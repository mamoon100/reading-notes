# Introduction to React and Components

#### Content:

- [What is a Component?](#what-is-a-component)
- [What are the charactistics of a component?](#what-are-the-charactistics-of-a-component)
- [What are the advantages of using component based architecture?](#what-are-the-advantages-of-using-component-based-architecture)
- [What is props short for?](#what-is-props-short-for)
- [How are props used in React?](#how-are-props-used-in-react)
- [What is the flow of props?](#what-is-the-flow-of-props)
- [Thing i want to know more about](#things-i-want-to-know-more-about)

#### What is a Component?

A component is a modular, portable, replaceable, and reusable set of well-defined functionality that encapsulates its implementation and exporting it as a higher-level interface.
A component is a software object, intended to interact with other components, encapsulating certain functionality or a set of functionalities. It has an obviously defined interface and conforms to a recommended behavior common to all components within an architecture.
A software component can be defined as a unit of composition with a contractually specified interface and explicit context dependencies only. That is, a software component can be deployed independently and is subject to composition by third parties.
Views of a Component
A component can have three different views − object-oriented view, conventional view, and process-related view.

Object-oriented view

A component is viewed as a set of one or more cooperating classes. Each problem domain class (analysis) and infrastructure class (design) are explained to identify all attributes and operations that apply to its implementation. It also involves defining the interfaces that enable classes to communicate and cooperate.

Conventional view

It is viewed as a functional element or a module of a program that integrates the processing logic, the internal data structures that are required to implement the processing logic and an interface that enables the component to be invoked and data to be passed to it.

Process-related view

In this view, instead of creating each component from scratch, the system is building from existing components maintained in a library. As the software architecture is formulated, components are selected from the library and used to populate the architecture.

A user interface (UI) component includes grids, buttons referred as controls, and utility components expose a specific subset of functions used in other components.

Other common types of components are those that are resource intensive, not frequently accessed, and must be activated using the just-in-time (JIT) approach.

Many components are invisible which are distributed in enterprise business applications and internet web applications such as Enterprise JavaBean (EJB), .NET components, and CORBA components.

#### What are the characteristics of a component?

Reusability − Components are usually designed to be reused in different situations in different applications. However, some components may be designed for a specific task.

Replaceable − Components may be freely substituted with other similar components.

Not context specific − Components are designed to operate in different environments and contexts.

Extensible − A component can be extended from existing components to provide new behavior.

Encapsulated − A A component depicts the interfaces, which allow the caller to use its functionality, and do not expose details of the internal processes or any internal variables or state.

Independent − Components are designed to have minimal dependencies on other components.

Principles of Component−Based Design
A component-level design can be represented by using some intermediary representation (e.g. graphical, tabular, or text-based) that can be translated into source code. The design of data structures, interfaces, and algorithms should conform to well-established guidelines to help us avoid the introduction of errors.

The software system is decomposed into reusable, cohesive, and encapsulated component units.

Each component has its own interface that specifies required ports and provided ports; each component hides its detailed implementation.

A component should be extended without the need to make internal code or design modifications to the existing parts of the component.

Depend on abstractions component do not depend on other concrete components, which increase difficulty in expendability.

Connectors connected components, specifying and ruling the interaction among components. The interaction type is specified by the interfaces of the components.

Components interaction can take the form of method invocations, asynchronous invocations, broadcasting, message driven interactions, data stream communications, and other protocol specific interactions.

For a server class, specialized interfaces should be created to serve major categories of clients. Only those operations that are relevant to a particular category of clients should be specified in the interface.

A component can extend to other components and still offer its own extension points. It is the concept of plug-in based architecture. This allows a plugin to offer another plugin API.

![Component](https://www.tutorialspoint.com/software_architecture_design/images/principles_of_component_based_design.jpg)

#### What are the advantages of using component based architecture?

1. Ease of deployment − As new compatible versions become available, it is easier to replace existing versions with no impact on the other components or the system as a whole.

2. Reduced cost − The use of third-party components allows you to spread the cost of development and maintenance.

3. Ease of development − Components implement well-known interfaces to provide defined functionality, allowing development without impacting other parts of the system.

4. Reusable − The use of reusable components means that they can be used to spread the development and maintenance cost across several applications or systems.

5. Modification of technical complexity − A component modifies the complexity through the use of a component container and its services.

6. Reliability − The overall system reliability increases since the reliability of each individual component enhances the reliability of the whole system via reuse.

7. System maintenance and evolution − Easy to change and update the implementation without affecting the rest of the system.

8. Independent − Independency and flexible connectivity of components. Independent development of components by different group in parallel. Productivity for the software development and future software development.

#### What is props short for?

React is a component-based library which divides the UI into little reusable pieces. In some cases, those components need to communicate (send data to each other) and the way to pass data between components is by using props.
“Props” is a special keyword in React, which stands for properties and is being used for passing data from one component to another.
But the important part here is that data with props are being passed in a uni-directional flow. (one way from parent to child)
Furthermore, props data is read-only, which means that data coming from the parent should not be changed by child components.

#### How are props used in React?

I will be explaining how to use Props step by step.
Firstly, define an attribute and its value(data)
Then pass it to child component(s) by using Props
Finally, render the Props Data
In my previous article, I’ve shown how to create & call a React component inside another component. So in this example, we have a ParentComponent including another component (child):

```
class ParentComponent extends React.Component {
    render() {
    return (
      <h1>
        I'm the parent component.
        <ChildComponent />
      </h1>
    );
  }
}
```

And this is our ChildComponent:

```
const ChildComponent = () => {
    return <p>I'm the 1st child!</p>;
}
```

The problem here is that, when we call the ChildComponent multiple times:

```
class ParentComponent extends Component {
  render() {
    return (
      <h1>
        I'm the parent component.
        <ChildComponent />
        <ChildComponent />
        <ChildComponent />
      </h1>
    );
  }
}
```

It always renders the same string again and again:

![prop](https://miro.medium.com/max/875/1*rzX4l1-rJn4c4_yeqooFbQ.png)

But what we like to do here is to get dynamic outputs, because each child component may have different data and let’s see how we can solve this issue by using props…

```
<ChildComponent someAttribute={value} anotherAttribute={value}/>
```

Here I’m declaring a “text” attribute to the ChildComponent and then assign a string value: “I’m the 1st child”.

```
<ChildComponent text={“I’m the 1st child”} />
```

Now the ChildComponent has a property and a value. Next, we need to pass it via Props.
2nd Step: Passing Data using Props
OK, now let’s take the “I’m the 1st child!” string and pass it by using props.
Passing props is very simple. Like we pass arguments to a function, we pass props into a React component and props bring all the necessary data.
Arguments passed to a function:

```
const addition = (firstNum, secondNum) => {
  return firstNum + secondNum;
};
```

Arguments passed to a React component:

```
const ChildComponent = (props) => {
  return <p>I'm the 1st child!</p>;
};
```

Final Step: Rendering Props Data
Alright so far, we have created an attribute and its value, then we passed it through props but we still can’t see it because we haven’t rendered it yet.
Prop is an Object
In the final step, we will render the props object by using string interpolation:

`{props}`

But first log props to console and see what it shows:

`console.log(props);`

As we can see, Props returns back an object. In JavaScript, we can access to object elements with dot(.) notation. So, let’s render our text property with interpolation:

```
const ChildComponent = (props) => {
  return <p>{props.text}</p>;
};
```

![](https://miro.medium.com/max/875/1*UuipOqB2yPyC1JPB8MTxpQ.png)

And that’s it! We’ve achieved to render the data coming from the parent component.
Before closing, let’s do the same for other child components:

```
class ParentComponent extends Component {
  render() {
    return (
      <h1>
        I'm the parent component.
        <ChildComponent text={"I'm the 1st child"} />
        <ChildComponent text={"I'm the 2nd child"} />
        <ChildComponent text={"I'm the 3rd child"} />
      </h1>
    );
  }
}
```

![](https://miro.medium.com/max/875/1*Kd52H-jKv6N1Cwgnaz4tOA.png)

#### What is the flow of props?

Props stand for properties and is a special keyword in React
Props are being passed to components like function arguments
Props can only be passed to components in one-way (parent to child)
Props data is immutable (read-only)

## Things I want to know more about

- How to pass data from component to component
- How to pass data from component to parent component

this thing is very important for me.
