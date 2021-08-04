# React and Forms

## What is a ‘Controlled Component’?

A controlled component is a component that renders form elements and controls them by keeping the form data in the component's state. In a controlled component, the form element's data is handled by the React component (not DOM) and kept in the component's state.

## Should we wait to store the users responses from the form into state when they submit the form OR should we update the state with their responses as soon as they enter them? Why.

we update the state with their responses as soon as they enter them

## How do we target what the user is entering if we have an event handler on an input field?

`event.target.value`

Starting With the Basics — The if statement
Using a conditional, like an if statement, allows us to specify that a certain block of code should be executed if a certain condition is met.
Consider the following example:
We have a person object that consists of a name, age, and driver property.

```js
let person = {
  name: "tony",
  age: 20,
  driver: null,
};
```

We want to test if the age of our person is greater than or equal to 16. If this is true, they’re old enough to drive and driver should say 'Yes'. If this is not true, driver should be set to 'No'.
We could use an if statement to accomplish this:

```js
if (person.age >= 16) {
  person.driver = "Yes";
} else {
  person.driver = "No";
}
```

But what if I told you we could do the same exact thing in just one line of code? Well, here it is:
person.driver = person.age >=16 ? 'Yes' : 'No';
This shorter code yields us the same result of person.driver = 'Yes';
Now that you’ve seen the conditional ternary operator in action, we can explore how it works!
The Conditional (Ternary) Operator
First, we’ll take a look at the syntax of a typical if statement:

```js
if ( condition ) {
  value if true;
} else {
  value if false;
}
```

Now, the ternary operator:
condition ? value if true : value if false
Here’s what you need to know:
The condition is what you’re actually testing. The result of your condition should be true or false or at least coerce to either boolean value.
A ? separates our conditional from our true value. Anything between the ? and the : is what is executed if the condition evaluates to true.
Finally a : colon. If your condition evaluates to false, any code after the colon is executed.
Example — Driver Age
We’ll take a moment to revisit the initial example in this article:

```js
let person = {
  name: "tony",
  age: 20,
  driver: null,
};
```

`person.driver = person.age >=16 ? 'Yes' : 'No'; `

The most important thing to note is the order of operations. Lets add some parenthesis to help you visualize the order in which code is executing:
`person.driver = ((person.age >=16) ? 'Yes' : 'No';)`
As you can hopefully now visualize, the very first thing that happens is our conditional is checking to see if person.age >=16 is true or false.
Since 20 is greater than 16, this evaluates to true. Here’s where we are now:
`person.driver = (true ? 'Yes' : 'No';)`
Since the condition of our conditional is true, the value between the ? and : is returned. In this case, that is 'Yes'.
Now that we have our return value, the final thing to do is to set it equal to our variable:
`person.driver = 'Yes';`
Awesome! Now lets move on to some more complex examples.

Rewrite the following statement using a ternary statement:

```js
if (x === y) {
  console.log(true);
} else {
  console.log(false);
}
```

`x===y ? console.log(true) : console.log(false);`
`console.log(x===y ? true : false);`

## Things I want to know more about

The forms design in react-bootstrap

and more about the state of the form
