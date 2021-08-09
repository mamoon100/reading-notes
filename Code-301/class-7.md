# REST

## Who is Roy Fielding?

Roy Thomas Fielding is an American computer scientist, one of the principal authors of the HTTP specification and the originator of the Representational State Transfer architectural style. He is an authority on computer network architecture and co-founded the Apache HTTP Server project.

## Why don’t the techniques that we use today work well when we need to be able to talk to all of the machines in the world?

Machines don't have a universal noun - that's why they suck. Every programming language, database, or other kind of system has a different way of talking about nouns. That's why the URL is so important. It let's all of these systems tell each other about each other's nouns.

## What is the HTTP protocol that Fielding and his friends created?

is all about applying verbs to nouns. For instance, when you go to a web page, the browser does an HTTP GET on the URL you typed in and back comes a web page.

Web pages usually have images, right? Those are separate resources. The web page just specifies the URLs to the images and the browser goes and does more GETs using the HTTP protocol on them until all the resources are obtained and the web page is displayed. But the important thing here is that very different kinds of nouns can be treated the same. Whether the noun is an image, text, video, an mp3, a slideshow, whatever. I can GET all of those things the same way given a URL.

## What does a **GET** do?

GET is used to request data from a specified resource.

GET is one of the most common HTTP methods.

## What does a **POST** do?

POST is used to send data to a server to create/update a resource.

## What does **PUT** do?

PUT method is used to update resource available on the server. Typically, it replaces whatever exists at the target URL with something else. You can use it to make a new resource or overwrite an existing one

## What does **PATCH** do?

A PATCH request is considered a set of instructions on how to modify a resource. Contrast this with PUT; which is a complete representation of a resource.

## Geocoding API

Did you get your API key? **YES**

## Weather Bit API

Did you get your API key? **YES**

## Yelp API Docs

Did you get your API key? **YES**

## The Movie DB API Docs

Did you get your API key? **YES**

## Things I want to know more about

the whole api market
