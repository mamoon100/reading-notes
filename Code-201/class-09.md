# Forms and JS Events

------------

*   ## Content
    * [Forms](#forms)
    * [Events](#events)

-----------------

### Forms
The ``<form>`` HTML element represents a document section containing interactive controls for submitting information.

example :

```
<form action="" method="get" class="form-example">
  <div class="form-example">
    <label for="name">Enter your name: </label>
    <input type="text" name="name" id="name" required>
  </div>
  <div class="form-example">
    <label for="email">Enter your email: </label>
    <input type="email" name="email" id="email" required>
  </div>
  <div class="form-example">
    <input type="submit" value="Subscribe!">
  </div>
</form>
```

<form action="" method="get" class="form-example">
  <div class="form-example">
    <label for="name">Enter your name: </label>
    <input type="text" name="name" id="name" required>
  </div>
  <div class="form-example">
    <label for="email">Enter your email: </label>
    <input type="email" name="email" id="email" required>
  </div>
  <div class="form-example">
    <input type="submit" value="Subscribe!">
  </div>
</form>


#### Attributes
This element includes the global attributes.

**accept-charset**
Space-separated character encodings the server accepts. The browser uses them in the order in which they are listed. The default value means the same encoding as the page.
(In previous versions of HTML, character encodings could also be delimited by commas.)
**autocapitalize**
A nonstandard attribute used by iOS Safari that controls how textual form elements should be automatically capitalized. autocapitalize attributes on a form elements override it on ``<form>``. Possible values:
>**none**: No automatic capitalization.

>**sentences** (default): Capitalize the first letter of each sentence.

>**words**: Capitalize the first letter of each word.

>**characters**: Capitalize all characters — that is, uppercase.

**autocomplete**
Indicates whether input elements can by default have their values automatically completed by the browser. autocomplete attributes on form elements override it on ``<form>``. Possible values:
off: The browser may not automatically complete entries. (Browsers tend to ignore this for suspected login forms; see The autocomplete attribute and login fields.)
on: The browser may automatically complete entries.
**name**
The name of the form. The value must not be the empty string, and must be unique among the form elements in the forms collection that it is in, if any.
**rel**
Creates a hyperlink or annotation depending on the value, see the rel attribute for details.


#### Attributes for form submission
The following attributes control behavior during form submission.

**action**
The URL that processes the form submission. This value can be overridden by a formaction attribute on a ``<button>``, ``<input type="submit">``, or ``<input type="image">``element.
**enctype**
If the value of the method attribute is post, enctype is the MIME type of the form submission. Possible values:

>**application/x-www-form-urlencoded**: The default value.

>**multipart/form-data**: Use this if the form contains`` <input> ``elements with type=file.

>**text/plain**: Introduced by HTML5 for debugging purposes.

This value can be overridden by formenctype attributes on ``<button>``,``<input type="submit">``, or ``<input type="image">`` elements.

**method**
The HTTP method to submit the form with. Possible (case insensitive) values:
post: The POST method; form data sent as the request body.
get: The GET method; form data appended to the action URL with a ? separator. Use this method when the form has no side-effects.
dialog: When the form is inside a ``<dialog>``, closes the dialog on submission.
This value is overridden by formmethod attributes on``<button>``,``<input type="submit">``, or ``<input type="image">`` elements.

**novalidate**
This Boolean attribute indicates that the form shouldn't be validated when submitted. If this attribute is not set (and therefore the form is validated), it can be overridden by a formnovalidate attribute on a ``<button>``, ``<input type="submit">``, or``<input type="image">`` element belonging to the form.
**target**
Indicates where to display the response after submitting the form. In HTML 4, this is the name/keyword for a frame. In HTML5, it is a name/keyword for a browsing context (for example, tab, window, or iframe). The following keywords have special meanings:
>**_self** (default): Load into the same browsing context as the current one.

>**_blank**: Load into a new unnamed browsing context.

>**_parent**: Load into the parent browsing context of the current one. If no parent, behaves the same as _self.

>**_top**: Load into the top-level browsing context (i.e., the browsing context that is an ancestor of the current one and has no parent). If no parent, behaves the same as _self.

This value can be overridden by a formtarget attribute on a ``<button>``,``<input type="submit">``, or ``<input type="image">`` element.

----------------------


### Events

Events are actions or occurrences that happen in the system you are programming, which the system tells you about so you can respond to them in some way if desired. For example, if the user selects a button on a webpage, you might want to respond to that action by displaying an information box. In this article, we discuss some important concepts surrounding events, and look at how they work in browsers. This won't be an exhaustive study; just what you need to know at this stage.

As mentioned above, events are actions or occurrences that happen in the system you are programming — the system produces (or "fires") a signal of some kind when an event occurs, and provides a mechanism by which an action can be automatically taken (that is, some code running) when the event occurs. For example, in an airport, when the runway is clear for take off, a signal is communicated to the pilot. As a result, the plane can safely takeoff.

![plane](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/Events/mdn-mozilla-events-runway.png)

In the case of the Web, events are fired inside the browser window, and tend to be attached to a specific item that resides in it — this might be a single element, set of elements, the HTML document loaded in the current tab, or the entire browser window. There are many different types of events that can occur. For example:

- The user selects a certain element or hovers the cursor over a certain element.
- The user chooses a key on the keyboard.
- The user resizes or closes the browser window.
- A web page finishes loading.
- A form is submitted.
- A video is played, paused, or finishes.
- An error occurs.

Each available event has an event handler, which is a block of code (usually a JavaScript function that you as a programmer create) that runs when the event fires. When such a block of code is defined to run in response to an event, we say we are registering an event handler. Note: Event handlers are sometimes called event listeners — they are pretty much interchangeable for our purposes, although strictly speaking, they work together. The listener listens out for the event happening, and the handler is the code that is run in response to it happening.

**A simple example**

Let's look at a simple example of what we mean here. You've already seen events and event handlers used in many of the examples, but let's recap just to cement our knowledge. In the following example, we have a single ```<button>```, which when pressed, makes the background change to a random color:

```
<button>Change color</button>
const btn = document.querySelector('button');
```
The JavaScript looks like so:

```
function random(number) {
  return Math.floor(Math.random() * (number+1));
}

btn.onclick = function() {
  const rndCol = 'rgb(' + random(255) + ',' + random(255) + ',' + random(255) + ')';
  document.body.style.backgroundColor = rndCol;
}
```

In this code, we store a reference to the button inside a constant called btn, using the Document.querySelector() function. We also define a function that returns a random number. The third part of the code is the event handler. The btn constant points to a ``<button>`` element, and this type of object has a number of events that can fire on it, and therefore, event handlers available. We are listening for the click event firing, by setting the onclick event handler property to equal an anonymous function containing code that generates a random RGB color and sets the ``<body>`` background-color equal to it.

This code is run whenever the click event fires on the ``<button>`` element, that is, whenever a user selects it.