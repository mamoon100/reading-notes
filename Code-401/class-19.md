# Spring and Sockets

Today we are going to learn about the basics of Spring Socket and how to use it to create a simple chat application.

Before we start let's see what is t a socket and how it works.

WebSockets is a bi-directional, full-duplex, persistent connection between a web browser and a server. Once a WebSocket connection is established the connection stays open until the client or server decides to close this connection.

Let's start by creating a simple chat application.

1. Enable web socket in spring boot

```java
@Configuration
@EnableWebSocketMessageBroker
public class WebSocketConfig extends AbstractWebSocketMessageBrokerConfigurer {

    @Override
    public void configureMessageBroker(MessageBrokerRegistry config) {
        config.enableSimpleBroker("/topic");
        config.setApplicationDestinationPrefixes("/app");
    }

    @Override
    public void registerStompEndpoints(StompEndpointRegistry registry) {
         registry.addEndpoint("/chat");
         registry.addEndpoint("/chat").withSockJS();
    }
}
```

2. Create the Message Model

```java

public class Message {

    private String from;
    private String text;

    // getters and setters
}
```

3. Create a Message-Handling Controller

```java
@MessageMapping("/chat")
@SendTo("/topic/messages")
public OutputMessage send(Message message) throws Exception {
    String time = new SimpleDateFormat("HH:mm").format(new Date());
    return new OutputMessage(message.getFrom(), message.getText(), time);
}
```

4. Create a Browser Client

```html
<html>
  <head>
    <title>Chat WebSocket</title>
    <script src="resources/js/sockjs-0.3.4.js"></script>
    <script src="resources/js/stomp.js"></script>
    <script type="text/javascript">
      var stompClient = null;

      function setConnected(connected) {
        document.getElementById("connect").disabled = connected;
        document.getElementById("disconnect").disabled = !connected;
        document.getElementById("conversationDiv").style.visibility = connected
          ? "visible"
          : "hidden";
        document.getElementById("response").innerHTML = "";
      }

      function connect() {
        var socket = new SockJS("/chat");
        stompClient = Stomp.over(socket);
        stompClient.connect({}, function (frame) {
          setConnected(true);
          console.log("Connected: " + frame);
          stompClient.subscribe("/topic/messages", function (messageOutput) {
            showMessageOutput(JSON.parse(messageOutput.body));
          });
        });
      }

      function disconnect() {
        if (stompClient != null) {
          stompClient.disconnect();
        }
        setConnected(false);
        console.log("Disconnected");
      }

      function sendMessage() {
        var from = document.getElementById("from").value;
        var text = document.getElementById("text").value;
        stompClient.send(
          "/app/chat",
          {},
          JSON.stringify({ from: from, text: text })
        );
      }

      function showMessageOutput(messageOutput) {
        var response = document.getElementById("response");
        var p = document.createElement("p");
        p.style.wordWrap = "break-word";
        p.appendChild(
          document.createTextNode(
            messageOutput.from +
              ": " +
              messageOutput.text +
              " (" +
              messageOutput.time +
              ")"
          )
        );
        response.appendChild(p);
      }
    </script>
  </head>
  <body onload="disconnect()">
    <div>
      <div>
        <input type="text" id="from" placeholder="Choose a nickname" />
      </div>
      <br />
      <div>
        <button id="connect" onclick="connect();">Connect</button>
        <button id="disconnect" disabled="disabled" onclick="disconnect();">
          Disconnect
        </button>
      </div>
      <br />
      <div id="conversationDiv">
        <input type="text" id="text" placeholder="Write a message..." />
        <button id="sendMessage" onclick="sendMessage();">Send</button>
        <p id="response"></p>
      </div>
    </div>
  </body>
</html>
```
