# Putting it all together

1. How would you break a mock into a component heirarchy?

The first thing you’ll want to do is to draw boxes around every component (and subcomponent) in the mock and give them all names. If you’re working with a designer, they may have already done this, so go talk to them! Their Photoshop layer names may end up being the names of your React components!

But how do you know what should be its own component? Use the same techniques for deciding if you should create a new function or object. One such technique is the single responsibility principle, that is, a component should ideally only do one thing. If it ends up growing, it should be decomposed into smaller subcomponents.

Since you’re often displaying a JSON data model to a user, you’ll find that if your model was built correctly, your UI (and therefore your component structure) will map nicely. That’s because UI and data models tend to adhere to the same information architecture. Separate your UI into components, where each component matches one piece of your data model.

![thinking-in-react-components](https://reactjs.org/static/eb8bda25806a89ebdc838813bdfa3601/6b2ea/thinking-in-react-components.png)

You’ll see here that we have five components in our app. We’ve italicized the data each component represents.

FilterableProductTable (orange): contains the entirety of the example
SearchBar (blue): receives all user input
ProductTable (green): displays and filters the data collection based on user input
ProductCategoryRow (turquoise): displays a heading for each category
ProductRow (red): displays a row for each product
If you look at ProductTable, you’ll see that the table header (containing the “Name” and “Price” labels) isn’t its own component. This is a matter of preference, and there’s an argument to be made either way. For this example, we left it as part of ProductTable because it is part of rendering the data collection which is ProductTable’s responsibility. However, if this header grows to be complex (e.g., if we were to add affordances for sorting), it would certainly make sense to make this its own ProductTableHeader component.

Now that we’ve identified the components in our mock, let’s arrange them into a hierarchy. Components that appear within another component in the mock should appear as a child in the hierarchy:

- FilterableProductTable
  - SearchBar
  - ProductTable
    - ProductCategoryRow
    - ProductRow

2. What is the single responsibility principle and how does it apply to components?

The single-responsibility principle (SRP) is a computer-programming principle that states that every module, class or function in a computer program should have responsibility over a single part of that program's functionality, and it should encapsulate that part. All of that module, class or function's services should be narrowly aligned with that responsibility.

3. What does it mean to build a ‘static’ version of your application?

has no interactivity (Do not use state)

4. Once you have a static application, what do you need to add?

Start To add The state

5. What are the three questions you can ask to determine if something is state?

   1. Is it passed in from a parent via props? If so, it probably isn’t state.
   2. Does it remain unchanged over time? If so, it probably isn’t state.
   3. Can you compute it based on any other state or props in your component? If so, it isn’t state.

6. How can you identify where state needs to live?

For each piece of state in your application:

- Identify every component that renders something based on that state.
- Find a common owner component (a single component above all the components that need the state in the hierarchy).
- Either the common owner or another component higher up in the hierarchy should own the state.
- If you can’t find a component where it makes sense to own the state, create a new component solely for holding the state and add it somewhere in the hierarchy above the common owner component.

Let’s run through this strategy for our application:

- ProductTable needs to filter the product list based on state and SearchBar needs to display the search text and checked state.
- The common owner component is FilterableProductTable.
- It conceptually makes sense for the filter text and checked value to live in FilterableProductTable

## Things I want to know more about

more usage of state and how to fix the delay in the updating state
