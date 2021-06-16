# Debugging 

JavaScript can be hard to learn and everyone makes mistakes when writing it. This chapter will help you learn how to find the errors in your code. It will also teach you how to write scripts that deal with potential errors gracefully.

When you are writing JavaScript, do not expect to write it perfectly the first time. Programming is like problem solving: you are given a puzzle and not only do you have to solve it, but you also need to create the instructions that allow the computer to solve it, too.

When writing a long script, nobody gets everything right in their first attempt. The error messages that a browser gives look cryptic at first, but they can help you determine what went wrong in your JavaScript and how to fix it. In this chapter you will learn about:

THE CONSOLE & DEV TOOLS
Tools built into the browser that help you hunt for errors.

COMMON PROBLEMS
Common sources of errors, and how to solve them.

HANDLING ERRORS
How code can deal with potential errors gracefully.

To find the source of an error, it helps to know how scripts are processed. The order in which statements are executed can be complex; some tasks cannot complete until another statement or function has been run:

```

2. function greetUser () {
    return 'He 11 o ' + getName ();
3. function getName() {
    var name= 'Molly ' ;
    return name;
1. var greeting= greetUser();
4. alert(greeting);

```

This script above creates a greeting message, then writes it to an alert box (see right-hand page). In order to create that greeting, two functions are used: greetUser () and getName () .

You might think that t he order of execution (the order in which st atements are processed) would be as numbered: one through to four. However, it is a little more complicated.

To complete step one, the interpreter needs the results of the functions in steps two and three (because the message contains values return ed by those functions). The order of execution is more like this: 1, 2, 3, 2, 1, 4.

1. The greeting variable gets its value from the greetUser () function.
2. greetUser() creates the message by combining the string 'He 11 o ' with the result of getName ().
3. getName () returns the name to greetUser() .
2. greetUser() now knows the name, and combines it with t he string. It then returns the message to the statement that called it in step 1.
1. The value of the greeting is stored in memory.
4. This greeting variable is written to an alert box.

Using an Alert for Simple Debugging

Problem

You want a simple way to check the value of a variable.

Solution

Use an alert message box to output the value of a variable:

``alert(someVariable);``

Discussion
Most developers use what I call the poor man’s debugging tool: printing out the value of a variable using whatever output functionality is available. With JavaScript, the poor man’s debugging usually occurs through an alert message box or with the JavaScript console, if the console is supported by the browser.

To use an alert message box to debug, just provide the variable in the function call:

``alert(variableName);``

If the variable is a simple scalar value, the result of this function call is a printout of the string value of the object’s contents. If the object is more complex, the print results will vary. For instance, an array will have a print out value like the following:

``var fruit = ['apple','cherry','pear'];``

``alert(fruit); // prints out apple, cherry, pear``

The array values are all printed out, in order, with a comma between the entries.

Using an object with the alert can have interesting effects. If you pass a variable containing a reference to a web page element, you may get unpredictable results depending on the browser used, its age, the DOM the browser supports, and so on. For the most part, though, and for most web page elements, the object printouts will be the same. In Safari 4, a variable with a reference to a div element:

``alert(divElement);``

prints out as:

[object HTMLDivElement]
Not particularly useful. However, the following could provide useful information:

``alert(divElement.innerHTML); // prints out contents of div element``

Anything beyond these simple printouts, though, should be left for browser debuggers.

Initiating Manageable Errors
Problem
You want to incorporate custom exceptions into your applications or libraries that provide useful information to calling applications.

Solution
Use the throw statement, and create a custom object as an exception:

if (typeof value == "number") {
    sum+=number;
} else {
   throw "NotANumber";
}
Discussion
The throw statement is partner to try...catch. With throw, you can throw exceptions rather than returning error values from functions or setting some global error value. The advantage to using throw and try...catch is that it doesn’t matter how deeply nested the error occurs, as the exception can ensure that the error is reflected to the calling application, and cleanly, too.

In the solution, the exception is thrown as a string. You can also throw an integer, Boolean, or object. If you only need to provide an exception message, use the string—or an integer if you’re using an array of exceptions, and the integer is used to look up the error. Otherwise, either create and throw a specific exception, or create a new Error object, providing your own error message:

```
if (typeof value == "number") {
    sum+=number;
} else {
   throw new Error("NotANumber");
}
```

The existing exception types are Error, as demonstrated, and:

EvalError
Used when eval is used improperly

RangeError
Used when the number is out of range

ReferenceError
Used when a nonexistent variable is referenced

SyntaxError
Used when there’s a syntax error

TypeError
Indicates an unexpected type

URIError
Used when a malformed URI is encountered

DOMException
Indicates a DOM error

EventException
Indicates a DOM event exception

RangeException
Indicates a DOM range exception

The last three exceptions are related to the DOM API. All the errors take a custom message as a string parameter.