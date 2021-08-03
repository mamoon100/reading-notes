# Passing Functions as Props

## What does .map() return?

New Array

## If I want to loop through an array and display each value in JSX, how do I do that in React?

```jsx
const numbers = [1, 2, 3, 4, 5];
const listItems = numbers.map((number) => <li>{number}</li>);
```

## Each list item needs a unique ------

Key

## What is the purpose of a key?

Keys help React identify which items have changed, are added, or are removed. Keys should be given to the elements inside the array to give the elements a stable identity:

## What is the spread operator?

InJavaScript, spread syntax refers to the use of an ellipsis of three dots (…) to expand an iterable object into the list of arguments.
“When ...arr is used in the function call, it ‘expands’ an iterable object arr into the list of arguments.” — JavaScript.info
The spread operator was added to JavaScript in ES6 (ES2015), just like the rest parameters, which have the same syntax: three magic dots ….

## What is ... used for?

“Spread operator to the rescue! It looks similar to rest parameters, also using ..., but does quite the opposite.” — JavaScript.info

## What else can … do?

The … spread operator is useful for many different routine tasks in JavaScript, including the following:
Copying an array
Concatenating or combining arrays
Using Math functions
Using an array as arguments
Adding an item to a list
Adding to state in React
Combining objects
Converting NodeList to an array

```js
const hello = { hello: "😋😛😜🤪😝" };
const world = { world: "🙂🙃😉😊😇🥰😍🤩!" };

const helloWorld = { ...hello, ...world };
console.log(helloWorld); // Object { hello: "😋😛😜🤪😝", world: "🙂🙃😉😊😇🥰😍🤩!" }
```

### In the video, what is the first step that the developer does to pass functions between components?

Declare The function

### In your own words, what does the increment function do?

increase the counter of the parent by one

### How can you pass a method from a parent component into a child component?

by passing the method as a prop

### How does the child component invoke a method that was passed to it from a parent component?

by calling the method this.props.increment()

## Things I want to know more about

1. i get throw somthing called this.setState,bind(this) and i want to know more about it.
