# HTML Lists, Control Flow with JS, and the CSS Box Model

-------

* ## Content:
    * [Lists](#lists)
    * [Boxes](#boxes)
    * [Basic JavaScript Instructions](#basic-javascript-instructions)
    * [Decisions and Loops](#decisions-and-loops)

### Lists
**There are lots of occasions when we need to use lists. HTML provides us with three different types:**

* Ordered lists are lists where each item in the list is numbered. For example, the list might be a set of steps for a recipe that must be performed in order, or a legal contract
where each point needs to be identified by a section number.
* Unordered lists are lists that begin with a bullet point (rather than characters that indicate order).
* Definition lists are made up of a set of terms along with the definitions for each of those terms.

> **Example:**
```
<html>
<head>
     <title>Lists</title>
</head>
<body>
    <h1>Scrambled Eggs</h1>
    <p>Eggs are one of my favourite foods. Here is a recipe for deliciously rich scrambled eggs.</p>
    <h2>Ingredients</h2>
    <ul>
	<li>2 eggs</li>
	<li>1tbs butter</li>
	<li>2tbs cream</li>
	</ul>
    <h2>Method</h2>
    <ol>
    <li>Melt butter in a frying pan over a medium heat</li>
	<li>Gently mix the eggs and cream in a bowl</li>
	<li>Once butter has melted add cream and eggs</li>
	<li>Using a spatula fold the eggs from the edge of the pan to the center every 20 seconds (as if you are making an omelette)</li>
	<li>When the eggs are still moist remove from the heat (it will continue to cook on the plate until served)</li>
    </ol>
</body>
</html>
```

-----

### Boxes
 **Box Dimensions width, height and Margin and padding**
 ![Box Modle](https://devopedia.org/images/article/289/5708.1602657423.png)

 * **Summary:**
    * CSS treats each HTML element as if it has its own box.
    * You can use CSS to control the dimensions of a box.
    * You can also control the borders, margin and padding for each box with CSS.
    * It is possible to hide elements using the display and visibility properties.
    * Block-level boxes can be made into inline boxes, and inline boxes made into block-level boxes.
    * Legibility can be improved by controlling the width of boxes containing text and the leading.
    * CSS3 has introduced the ability to create image borders and rounded borders.

----

### Basic JavaScript Instructions

**WHAT IS A VARIABLE?**
> A script w ill have to temporarily store the bits of info rmation it needs to do its job. It can store t his data in variables.

**RULES FOR NAMING VARIABLES**
1. The name must begin with a letter, dollar sign ($),or an underscore (_). It must not start with a number.
2. The name can contain letters,numbers, dollar sign ($), or an underscore (_). Note that you must not use a dash(-) or a period (.) in a variable name.
3. You cannot use keywords or reserved words. Keywords are special words that tell the interpreter to do something. For example, var is a keyword used to declare a variable. Reserved words are ones t hat may be used in a future version of JavaScript.
4. All variables are case sensitive, so score and Score would be different variable names, but it is bad practice to create two variables t hat have the same name using different cases.
5. Use a name that describes the kind of information that the variable stores. For example, fi rstName might be used to store a person's first name, lastName for t heir last name, and age for their age.
6. If your variable name is made up of more than one word, use a capital letter for the first letter of every word after the first word. For example, f i rstName rather than firstName (this is referred to as camel case).You can also use an underscore between each word (you cannot use a dash).

### Decisions and Loops
**USING IF STATEMENTS**

```
var score = 75 //Score  
var msg;      //Message

i f (score>= 50) {
//If score is 50 or higher
msg = 'Congratulations!';
msg += ' Proceed to the next round . ' ;
}
var el = document.getElementByld('answer ' ) ;
el .textContent = msg;
```

> Result:
> Congratulations! Proceed to the next round.

