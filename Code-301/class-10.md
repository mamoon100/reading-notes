# In memory storage

## What is a ‘call’?

At the most basic level, a call stack is a data structure that uses the Last In, First Out (LIFO) principle to temporarily store and manage function invocation (call).

## How many ‘calls’ can happen at once?

It is single-threaded. Meaning it can only do one thing at a time

## What does LIFO mean?

Last In, First Out

## Draw an example of a call stack and the functions that would need to be invoked to generate that call stack.

```js
function firstFunction() {
  throw new Error("Stack Trace Error");
}

function secondFunction() {
  firstFunction();
}

function thirdFunction() {
  secondFunction();
}

thirdFunction();
```

## What causes a Stack Overflow?

A stack overflow occurs when there is a recursive function (a function that calls itself) without an exit point. The browser (hosting environment) has a maximum stack call that it can accomodate before throwing a stack error.

## What is a ‘refrence error’?

This is as simple as when you try to use a variable that is not yet declared you get this type os errors.

## What is a ‘syntax error’?

I know it’s in the name of the errors, but like it says itself, this occurs when you have something that cannot be parsed in terms of syntax, like when you try to parse an invalid object using JSON.parse.

## What is a ‘range error’?

Try to manipulate an object with some kind of length and give it an invalid length and this kind of errors will show up.

## What is a ‘tyep error’?

Like the name indicates, this types of errors show up when the types (number, string and so on) you are trying to use or access are incompatible, like accessing a property in an undefined type of variable.

## What is a breakpoint?

it's when debugging to prevent the complier to go any further than you want

## What does the word ‘debugger’ do in your code?

run the code and get all the info and variable inside

## Things I want to know more about

How to Debug node and/or react app in vsCode
