# State and Props

## Based on The Diagram The render will happen before the componentDidMount

## The first thing will happen in react lifecycle is MOUNTING

## In order

## 1. Constructor

## 2. RENDER

## 3. ComponentDidMount

## 4. React Updates

## 5. componentWillUnmount

### componentDidMount()

This method is invoked immediately after a component is mounted. If you need to load anything using a network request or initialize the DOM, it should go here. This method is a good place to set up any subscriptions. If you do that, don’t forget to unsubscribe in componentWillUnMount().
setState() can be called here, but it should be used sparingly, because it will cause a re-render, which can lead to performance issues.
Here we use componentDidMount() to connect to the YouTube API and get videos when the components is rendered.

```javascript
componentDidMount() {
console.log(‘got videos’);
this.getVideos(‘cats’);
}
getVideos(query) {
var options = {
key: this.props.YOUTUBE_API_KEY,
query: query
};
```

## You Can pass any data type to the props

## Basically, the difference is that state is something like attributes in OOP : it's something local to a class (component), used to better describe it. Props are like parameters - they are passed to a component from the caller of a component (the parent) : as if you called a function with certain parameters.

![React stat vs props](https://i.stack.imgur.com/wqvF2.png)

## React components automatically re-render whenever there is a change in their state or props

## Things we can store it in state are:

1. A simple value
2. An object
3. An array
4. A function
5. String

## Things I want to know more about

I know how bootstrap works, but I want to know more about how react bootstrap works and add some more design to the page.

I also want to know more about Netlify and why we should use it instead of GitHub Pages.
