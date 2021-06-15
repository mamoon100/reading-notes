# Layout

------------

## CSS layout

At this point we've already looked at CSS fundamentals, how to style text, and how to style and manipulate the boxes that your content sits inside. Now it's time to look at how to place your boxes in the right place in relation to the viewport, and one another. We have covered the necessary prerequisites so we can now dive deep into CSS layout, looking at different **display** settings, modern layout tools like **flex**box, CSS grid, and positioning, and some of the legacy techniques you might still want to know about.


This article will recap some of the CSS layout features we've already touched upon in previous modules — such as different ****display**** values — and introduce some of the concepts we'll be covering throughout this module.

**Prerequisites**: The basics of HTML (study Introduction to HTML), and an idea of How CSS works (study Introduction to CSS.)
**Objective**: To give you an overview of CSS page layout techniques. Each technique can be learned in greater detail in subsequent tutorials.

CSS page layout techniques allow us to take elements contained in a web page and control where they are positioned relative to their default position in normal layout flow, the other elements around them, their parent container, or the main viewport/window.  The page layout techniques we'll be covering in more detail in this module are

* Normal flow
* The **display** property
* **flex**box
* Grid
* Floats
* Positioning
* Table layout
* Multiple-column layout

Each technique has its uses, advantages, and disadvantages, and no technique is designed to be used in isolation. By understanding what each method is designed for you will be in a good place to understand which is the best layout tool for each task.

**Normal flow**

Normal flow is how the browser lays out HTML pages by default when you do nothing to control page layout. Let's look at a quick HTML example:

```
<p>I love my cat.</p>

<ul>
  <li>Buy cat food</li>
  <li>Exercise</li>
  <li>Cheer up friend</li>
</ul>

<p>The end!</p>
```

By default, the browser will **display** this code as follows:

<p>I love my cat.</p>
<ul>
  <li>Buy cat food</li>
  <li>Exercise</li>
  <li>Cheer up friend</li>
</ul>
<p>The end!</p>

**The **display** property**

The main methods of achieving page layout in CSS are all values of the **display** property. This property allows us to change the default way something **display**s. Everything in normal flow has a value of **display**, used as the default way that elements they are set on behave. For example, the fact that paragraphs in English **display** one below the other is due to the fact that they are styled with **display**: **block**. If you create a link around some text inside a paragraph, that link remains **inline** with the rest of the text, and doesn’t break onto a new line. This is because the ``<a>`` element is **display**: **inline** by default.

You can change this default **display** behavior. For example, the ``<li>`` element is **display**: **block** by default, meaning that list items **display** one below the other in our English document. If we change the **display** value to **inline** they now **display** next to each other, as words would do in a sentence. The fact that you can change the value of **display** for any element means that you can pick HTML elements for their semantic meaning, without being concerned about how they will look. The way they look is something that you can change.

In addition to being able to change the default presentation by turning an item from **block** to **inline** and vice versa, there are some bigger layout methods that start out as a value of **display**. However, when using these, you will generally need to invoke additional properties. The two values most important for our purposes when discussing layout are **display**: **flex** and **display**: **grid**.


**Flexbox**

Flexbox is the short name for the Flexible Box Layout Module, designed to make it easy for us to lay things out in one dimension — either as a row or as a column. To use flexbox, you apply display: flex to the parent element of the elements you want to lay out; all its direct children then become flex items. We can see this in a simple example.

The HTML markup below gives us a containing element, with a class of wrapper, inside which are three ``<div>`` elements. By default these would display as block elements, below one another, in our English language document.

However, if we add display: flex to the parent, the three items now arrange themselves into columns. This is due to them becoming flex items and being affected by some initial values that flexbox sets on the flex container. They are displayed in a row, because the initial value of flex-direction set on their parent is row. They all appear to stretch to the height of the tallest item, because the initial value of the align-items property set on their parent is stretch. This means that the items stretch to the height of the flex container, which in this case is defined by the tallest item. The items all line up at the start of the container, leaving any extra space at the end of the row.
```
.wrapper {
  display: flex;
}
```

```
<div class="wrapper">
  <div class="box1">One</div>
  <div class="box2">Two</div>
  <div class="box3">Three</div>
</div>
```

<div class="wrapper" style="display: flex;">
  <div class="box1" style="border-radius: 5px; background-color: rgb(207,232,220); padding: 1em; ">One</div>
  <div class="box2" style="border-radius: 5px; background-color: rgb(207,232,220); padding: 1em; ">Two</div>
  <div class="box3" style="border-radius: 5px; background-color: rgb(207,232,220); padding: 1em; ">Three</div>
</div>



