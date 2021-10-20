# WRRC and Java

High LeveL HTTP and the Steps it take to made it work

Step 1: Local Parsing (Request)
When you open "http//www.example.com" in your browser the browser will extract the intend name "example.com" now it need to resolve the name to a IP address.

Step 2: Resolving the name to an IP address (DNS)
Now The DNS request contains the preconfigured IP address of the, now your request have to travel many network to find the IP address of the server, once the IP address is found it will be stored in the cache.

Step 3: TCP Connection
Now the request is sent to the server and the server will respond with the data the request is send over TCP

Step 4: HTTP Request
Now since the client has an IP address and a TCP connection, it can finally send an HTTP request!

Step 5: Tearing Down and Cleaning Up
After the request is sent the server will respond with the data and the client will receive the data and the TCP connection will be closed.

---

simple http request with java

1. create a request

```java
URL url = new URL("http://example.com");
HttpURLConnection con = (HttpURLConnection) url.openConnection();
con.setRequestMethod("GET");
```

2. adding request parameters

```java
Map<String, String> parameters = new HashMap<>();
parameters.put("param1", "val");

con.setDoOutput(true);
DataOutputStream out = new DataOutputStream(con.getOutputStream());
out.writeBytes(ParameterStringBuilder.getParamsString(parameters));
out.flush();
out.close();
```

```java
public class ParameterStringBuilder {
    public static String getParamsString(Map<String, String> params)
      throws UnsupportedEncodingException{
        StringBuilder result = new StringBuilder();

        for (Map.Entry<String, String> entry : params.entrySet()) {
          result.append(URLEncoder.encode(entry.getKey(), "UTF-8"));
          result.append("=");
          result.append(URLEncoder.encode(entry.getValue(), "UTF-8"));
          result.append("&");
        }

        String resultString = result.toString();
        return resultString.length() > 0
          ? resultString.substring(0, resultString.length() - 1)
          : resultString;
    }
}
```

3. Setting Request Headers

```java
con.setRequestProperty("Content-Type", "application/json");
String contentType = con.getHeaderField("Content-Type");
```

4. Configuring Timeouts

```java
con.setConnectTimeout(5000);
con.setReadTimeout(5000);
```

5. Handling Cookies

```java
String cookiesHeader = con.getHeaderField("Set-Cookie");
List<HttpCookie> cookies = HttpCookie.parse(cookiesHeader);
cookies.forEach(cookie -> cookieManager.getCookieStore().add(null, cookie));
Optional<HttpCookie> usernameCookie = cookies.stream()
  .findAny().filter(cookie -> cookie.getName().equals("username"));
if (usernameCookie == null) {
    cookieManager.getCookieStore().add(null, new HttpCookie("username", "john"));
}
con.disconnect();
con = (HttpURLConnection) url.openConnection();

con.setRequestProperty("Cookie",
  StringUtils.join(cookieManager.getCookieStore().getCookies(), ";"));
```

6. Reading Response

```java
int status = con.getResponseCode();
BufferedReader in = new BufferedReader(
  new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer content = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    content.append(inputLine);
}
in.close();
con.disconnect();
```
