# CRUD

## In your own words, describe what each group of status code represents

## 100’s =

This class of status code indicates a provisional response, consisting only of the Status-Line and optional headers, and is terminated by an empty line. There are no required headers for this class of status code. Since HTTP/1.0 did not define any 1xx status codes, servers MUST NOT send a 1xx response to an HTTP/1.0 client except under experimental conditions.

## 200’s =

This class of status code indicates that the client's request was successfully received, understood, and accepted.

## 300’s =

Further action is needed to fulfill the request. Often, these status codes are used for redirection. Google recommends that you use fewer than five redirects for each request. You can use Webmaster Tools to see if Google bot is having trouble crawling your redirected pages. The Crawl errors page in Googles website under Diagnostics lists any URLs that Google bot was unable to crawl due to redirect errors.

## 400’s =

These status codes indicate that there was likely an error in the request which prevented the server from being able to process it.

## 500’s =

These status codes indicate that the server had an internal error when trying to process the request. These errors tend to be with the server itself, not with the request.

## What is a status code 202?

The request was successful and the server created a new resource.
The request has been fulfilled and resulted in a new resource being created. The newly created resource can be referenced by the URI(s) returned in the entity of the response, with the most specific URI for the resource given by a Location header field. The response SHOULD include an entity containing a list of resource characteristics and location(s) from which the user or user agent can choose the one most appropriate. The entity format is specified by the media type given in the Content-Type header field. The origin server MUST create the resource before returning the 201 status code. If the action cannot be carried out immediately, the server SHOULD respond with 202 (Accepted) response instead.

A 201 response MAY contain an ETag response header field indicating the current value of the entity tag for the requested variant just created, see ETag section below.

## What is a status code 308?

This code is used in the resumable HTTP Requests Proposal to resume aborted PUT or POST requests

## What code would you use if an update didn’t return data to a client?

500

## What code would you use if a resource used to exist but no longer does?

410

## What is the ‘Forbidden’ status code?

403

## Why do we need to pull our MongoDB database string out of our server and put it into our .env?

The URL

## What is middleware?

code that runs before the final route call back.
They are in the middle of the beginning of the route and the
callback function.

## What does app.use(express.json()) do?

Returns middleware that parses both json and urlencoded. The options are passed to both middleware.

## What does the /:id mean in a route?

Route parameters are named URL segments that are used to capture the values specified at their position in the URL. The captured values are populated in the req.params object, with the name of the route parameter specified in the path as their respective keys.

## What is the difference beween PUT and PATCH?

The main difference between the PUT and PATCH method is that the PUT method uses the request URI to supply a modified version of the requested resource which replaces the original version of the resource, whereas the PATCH method supplies a set of instructions to modify the resource.

## How do you make a defalut value in a schema?

```js
const schema = new Schema({
  name: String,
  role: { type: String, default: "guitarist" },
});
```

## What does a 500 error status code mean?

This error response is a generic "catch-all" response.
500 Internal Server Error server error response code indicates
that the server encountered an unexpected condition that prevented
it from fulfilling the request.

## What is the difference between a status 200 and a status 201?

The 200 status code is by far the most common returned. It means, simply, that the request was received and understood and is being processed. A 201 status code indicates that a request was successful and as a result, a resource has been created (for example a new page).

## Things I want to know more about

Data base in general and mongo in special
