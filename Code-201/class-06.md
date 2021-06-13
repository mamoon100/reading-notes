# Problem Domain, Objects, and the DOM

---------

* ### Content:
    * **[Problem Domain](#problem-domain).**
    * **[Objects](#objects).**
    * **[Dom](#dom).**

-------


### Problem Domain
**What is Problem Domain:**
> is an engineering term referring to all information that defines the problem and constrains the solution.

**Why problem domains are hard**
Have you ever tried to put together a jigsaw puzzle that didn’t have any picture on it?  How about one like this one, that has a very similar pattern repeated on it and is double-sided?

![Hard jigsawq puzzle](https://simpleprogrammer.com/ezoimgfmt/spzone-simpleprogrammer.netdna-ssl.com/wp-content/uploads/2013/07/81zQGlKs9oS._SL1500_.jpg?ezimgfmt=rs:373x373/rscb2/ng:webp/ngcb2)

hard puzzle problem domain
The reason why puzzles like this one are so hard, is because you can’t really see what you are trying to build very clearly.  Normally when you put together a jigsaw puzzle you follow steps that might look something like this:

1. Figure out what the major components of the picture are
2. Sort the pieces by color or component
3. Put together all the border pieces
4. Put together each component of the picture from the piles you created


**You can often make the problem domain easier by cutting out cases and narrowing your focus to a particular part of the problem.**

------------------

### Objects

**Objects**.
JavaScript object is a standalone entity that holds multiple values in terms of properties and methods. Object property stores a literal value and method represents function. An object can be created using object literal or object constructor syntax.

Example:

``let person = {firstName:"John", lastName:"Doe", age:50, eyeColor:"blue"}``


------------------


### Dom

**What is the DOM?**
The Document Object Model (DOM) is a programming interface for HTML and XML documents. It represents the page so that programs can change the document structure, style, and content. The DOM represents the document as nodes and objects. That way, programming languages can connect to the page.

A Web page is a document. This document can be either displayed in the browser window or as the HTML source. But it is the same document in both cases. The Document Object Model (DOM) represents that same document so it can be manipulated. The DOM is an object-oriented representation of the web page, which can be modified with a scripting language such as JavaScript.

For example, the standard DOM specifies that the querySelectorAll method in the code below must return a list of all the <p> elements in the document:

``const paragraphs = document.querySelectorAll("p");``
``// paragraphs[0] is the first <p> element``
``// paragraphs[1] is the second <p> element, etc.``
``alert(paragraphs[0].nodeName);``

**Accessing the DOM
**You don't have to do anything special to begin using the DOM. Different browsers have different implementations of the DOM, and these implementations exhibit varying degrees of conformance to the actual DOM standard (a subject we try to avoid in this documentation), but every web browser uses some document object model to make web pages accessible via JavaScript.

When you create a script–whether it's inline in a ``<script>`` element or included in the web page by means of a script loading instruction–you can immediately begin using the API for the document or window elements to manipulate the document itself or to get at the children of that document, which are the various elements in the web page. Your DOM programming may be something as simple as the following, which displays an alert message by using the alert() function from the window object, or it may use more sophisticated DOM methods to actually create new content, as in the longer example below.

This following JavaScript will display an alert when the document is loaded (and when the whole DOM is available for use):

``<body onload="window.alert('Welcome to my home page!');">``

Another example. This function creates a new H1 element, adds text to that element, and then adds the H1 to the tree for this document:

```
<html>
  <head>
    <script>
       // run this function when the document is loaded
       window.onload = function() {

         // create a couple of elements in an otherwise empty HTML page
         const heading = document.createElement("h1");
         const heading_text = document.createTextNode("Big Head!");
         heading.appendChild(heading_text);
         document.body.appendChild(heading);
      }
    </script>
  </head>
  <body>
  </body>
</html>
```
-----------------------