![reactArrow](../img/reactArrow.png)
## Example of React Arrow Function

When writing an arrow function, there are a couple of things you can do to simplify it:
if the function only returns something (i.e the first work of the function body is `return`) you can use an `implicit return` by getting rid of the wrapping curly brackets and the `return` keyword

So:
```js
const myFunction = (message) => {
  return message.toUpperCase();
}
```
Would become:
```js
const myFunction = (message) => message.toUpperCase();
```
Additionally, if you have only one parameter, you can get rid of the brackets around the parameter:
```js
const myFunction = message => message.toUpperCase();
```
In React, this becomes:
```js
const MyComponent = props => <div>{props.message}</div>;
```
The above is the same as:
```js
const MyComponent = (props) => {
  return <div>{props.message}</div>;
}
```
This type of component is called a pure/functional/stateless component;
- functional because it is a function
- stateless because it doesn’t manage any state
- pure because it is a _pure_ function (if you want to google what that means)

As with any function, the value of the parameters is defined by the context in which the function is called, not the context in which it is defined.
So with a functional component (or any component, actually), the value of the props is determined from the context in which the component is rendered, so to pass a message prop into the above `MyComponent`, we would render it in some parent context like this:
```js
<MyComponent message="Hello World" />
```
When a component gets rendered, React behind the scenes calls the function and assigns the props, so the above is actually like doing:
```js
MyComponent({ message: 'Hello World' });
```
Where you are invoking the `MyComponent` function with an object with a message property. but it’s just written in JSX React syntax instead of standard JavaScript.

[Functions for Beginners Javascript](https://www.panayiotisgeorgiou.net/arrow-functions-beginners-javascript/)
#### [Return: Express README](../README.md)
