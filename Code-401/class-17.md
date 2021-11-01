# Spring Authorization

in the previous read we talk about spring security and how to use it to secure our application, in this read we will continue on spring security and how to let the user sign up or login by using third party application like google or github.

We will let the user by something called 0Auth2, this is a third party application that will allow the user to sign up or login by using google or github and then we will use the token that we get from the third party application to authenticate the user.

How to do this?

1. First we need to configure the spring security to use the 0Auth2.

```yml
application.yml
spring:
  security:
    oauth2:
      client:
        registration:
          github:
            clientId: github-client-id
            clientSecret: github-client-secret
```

Then you need to add the home page and the login page.

```html
<div class="container unauthenticated">
  With GitHub: <a href="/oauth2/authorization/github">click here</a>
</div>
<div class="container authenticated" style="display:none">
  Logged in as: <span id="user"></span>
</div>
```

```javascript
<script type="text/javascript">
    $.get("/user", function(data) {
        $("#user").html(data.name);
        $(".unauthenticated").hide()
        $(".authenticated").show()
    });
</script>
```

now let's add controller that will return the current user to the client.

```java
   @GetMapping("/user")
    public Map<String, Object> user(@AuthenticationPrincipal OAuth2User principal) {
        return Collections.singletonMap("name", principal.getAttribute("name"));
    }
```

Andd that's it (almost) now you can sign in and sign yp using github for example.
