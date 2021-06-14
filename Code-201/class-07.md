# Object-Oriented Programming, HTML Tables

-------

* ## Content:
    * [Domain Modeling](#domain-modeling)
    * [Table](#table)

----------

### Domain Modeling

domain modeling is the process of creating a conceptual model in code for a specific problem. A model describes the various entities, their attributes and behaviors, as well as the constraints that govern the problem domain. An entity that stores data in properties and encapsulates behaviors in methods is commonly referred to as an object-oriented model.

A domain model that's articulated well can verify and validate the understanding of a specific problem among various stakeholders. As a communication tool, it defines a vocabulary that can be used within and between both technical and business teams.

Model epic fails videos
Imagine you've been tasked to build a program that models the popularity of epic fail videos. After months of painstaking research, you've determined that the two essential metrics for gauging popularity are an epic rating and whether or not the video has animals.

Since you'll be modeling the popularity of many types of videos—parkour epic fails, corgi epic fails, etc.—you'll want to build self-contained objects with the same attributes and behaviors. That way, when you need to change the algorithm for determining popularity, the changes will be small and targeted.

As you read this article, type out and run all code samples you come across. Do not copy and paste. Writing out and testing your code will help you remember how to implement domain models in JavaScript later.

Define a constructor and initialize properties
To define the same properties between many objects, you'll want to use a constructor function. Below is a table that summarizes a JavaScript representation of an EpicFailVideo object.

Here's an implementation of the EpicFailVideo constructor function.

```
var EpicFailVideo = function(epicRating, hasAnimals) {
  this.epicRating = epicRating;
  this.hasAnimals = hasAnimals;
}

var parkourFail = new EpicFailVideo(7, false);
var corgiFail = new EpicFailVideo(4, true);

console.log(parkourFail);
console.log(corgiFail);
```

As you can see, the constructor function is defined using a function expression. In other words, the variable EpicFailVideo is declared and then assigned a function with two parameters called epicRating and hasAnimals.

When the function is called, the data inside these parameters are stored inside the this.epicRating and this.hasAnimals properties respectively. Storing data within properties ensures any newly created object can access that data later.

After the constructor function definition, two objects are instantiated with the new keyword and their properties are initialized by calling the EpicFailVideo constructor function. After being instantiated and initialized, these objects are stored inside the parkourFail and corgiFail variables.

Finally, the two newly created objects are logged to the console.

![the score](https://camo.githubusercontent.com/55928963ae0dc919186799ab35c1cd669724ddbeb0658d0ca4b9e79b38e1804e/68747470733a2f2f692e696d6775722e636f6d2f47326250456c462e706e67)


This is object-oriented programming in JavaScript at its most fundamental level.

1. The new keyword instantiates (i.e. creates) an object.
2. The constructor function initializes properties inside that object using the this variable.
3. The object is stored in a variable for later use.

-------------

### Table

The ``<table>`` HTML element represents tabular data — that is, information presented in a two-dimensional table comprised of rows and columns of cells containing data.

```
<table>
    <thead>
        <tr>
            <th colspan="2">The table header</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>The table body</td>
            <td>with two columns</td>
        </tr>
    </tbody>
</table>
```
<table>
    <thead>
        <tr>
            <th colspan="2">The table header</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>The table body</td>
            <td>with two columns</td>
        </tr>
    </tbody>
</table>

* Attributes
    * **align**  This enumerated attribute indicates how the table must be aligned inside the containing document. It may have the following values:

    > **left:** the table is displayed on the left side of the document;

    > **center:** the table is displayed in the center of the document;
    > **right:** the table is displayed on the right side of the document.

    * Set **margin-left**and **margin-right** to auto or **margin** to 0 auto to achieve an effect that is similar to the align attribute.

    * **bgcolor**  The background color of the table. It is a 6-digit hexadecimal RGB code, prefixed by a '#'. One of the predefined color kewords can also be used.

    > To achieve a similar effect, use the CSS background-color property.

    * **border** This integer attribute defines, in pixels, the size of the frame surrounding the table. If set to 0, the frame attribute is set to void.

    * To achieve a similar effect, use the CSS border shorthand property.

    * **cellpadding**  This attribute defines the space between the content of a cell and its border, displayed or not. If the cellpadding's length is defined in pixels, this pixel-sized space will be applied to all four sides of the cell's content. If the length is defined using a percentage value, the content will be centered and the total vertical space (top and bottom) will represent this value. The same is true for the total horizontal space (left and right).

    * To achieve a similar effect, apply the border-collapse property to the ``<table>`` element, with its value set to collapse, and the padding property to the ``<td>`` elements.

    * **cellspacing**  This attribute defines the size of the space between two cells in a percentage value or pixels. The attribute is applied both horizontally and vertically, to the space between the top of the table and the cells of the first row, the left of the table and the first column, the right of the table and the last column and the bottom of the table and the last row.

    * To achieve a similar effect, apply the border-spacing property to the ``<table>`` element. border-spacing does not have any effect if border-collapse is set to collapse.

    * **frame**  This enumerated attribute defines which side of the frame surrounding the table must be displayed.

    * To achieve a similar effect, use the **border-style** and **border-width** properties.

    * **rules** This enumerated attribute defines where rules, i.e. lines, should appear in a table. It can have the following values:

    > **none**, which indicates that no rules will be displayed; it is the default value;

    > **groups**, which will cause the rules to be displayed between row groups (defined by the ``<thead>``, ``<tbody>`` and ``<tfoot>`` elements) and between column groups (defined by the ``<col>`` and ``<colgroup>`` elements) only;

    > **rows**, which will cause the rules to be displayed between rows;

    > **columns**, which will cause the rules to be displayed between columns;

    > **all**, which will cause the rules to be displayed between rows and columns.

    * To achieve a similar effect, apply the border property to the appropriate ``<thead>``, ``<tbody>``, ``<tfoot>``, ``<col>``, or ``<colgroup>`` elements.

**summary** 
This attribute defines an alternative text that summarizes the content of the table. Use the ``<caption>`` element instead.
width 

This attribute defines the width of the table. Use the CSS width property instead.

--------------