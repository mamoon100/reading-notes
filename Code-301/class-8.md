# APIS

## What does REST stand for?

Representational State Transfer

## REST APIs are designed around a \_\_\_\_.

resources, which are any kind of object, data, or service that can be accessed by the client.

## What is an identifer of a resource? Give an example.

which is a URI that uniquely identifies that resource. For example, the URI for a particular customer order might be:

```http
https://adventure-works.com/orders/1
```

## What are the most common HTTP verbs?

GET, POST, PUT, PATCH, and DELETE.

## What should the URIs be based on?

should be based on nouns (the resource) and not verbs (the operations on the resource).

## Give an example of a good URI.

https://adventure-works.com/orders

## What does it mean to have a ‘chatty’ web API? Is this a good or a bad thing?

Such an API may require a client application to send multiple requests to find all of the data that it requires. Instead, you might want to denormalize the data and combine related information into bigger resources that can be retrieved with a single request. However, you need to balance this approach against the overhead of fetching data that the client doesn't need. Retrieving large objects can increase the latency of a request and incur additional bandwidth costs

It's a Bad thing

## What status code does a successful **GET** request return?

A successful GET method typically returns HTTP status code 200 (OK)

## What status code does an unsuccessful **GET** request return?

If the resource cannot be found, the method should return 404 (Not Found).

## What status code does a successful **POST** request return?

If a POST method creates a new resource, it returns HTTP status code 201

## What status code does a successful **DELETE** request return?

f the delete operation is successful, the web server should respond with HTTP status code 204 (No Content)

## Things I want to know more about

The Back end api and like how to make the file more privacy
