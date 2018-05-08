![reactBind](../img/reactBind.png)
## Bind a Method

___`this` is a special keyword inside each function that refers to the current context.___

In JavaScript, the value of `this` depends on how the function was called, not where or when it was defined. Also, it is not affected by scope, like a variable would be. This means, that whenever you pass a function down another function, this will not refer to the same value.
```js
function myFunction() {
 console.log(this);
}
// Calling the function normally
myFunction(); // 'this' will refer to 'window'

// pass the function to an object and call it as an object method
var myObj = { doSomething: myFunction};
myObj.doSomething; // 'this' will refer to 'myObj'
```
If a method refers to `this`, then it must be bounded within the component’s constructor.
These tend to be methods which rely on `this.state` or `this.props`, and also methods which call other methods, `this.setState()`.

There are at least five ways to handle the this context in React.
- Approach 1: Use React.createClass
```js
var HelloWorld = React.createClass({
  getInitialState() {
    return { message: 'Hi' };
  },

  logMessage() {
    // this magically works because React.createClass autobinds.
    console.log(this.state.message);
  },

  render() {
    return (
      <input type="button" value="Log" onClick={this.logMessage} />
    );
  }
});
```
- Approach 2: Bind in Render
```js
class HelloWorld extends React.Component {
  constructor(props) {
    super(props);
    this.state = { message: 'Hi' };
  }

  logMessage() {
    // This works because of the bind in render below.
    console.log(this.state.message);
  }

  render() {
    return (
      <input type="button" value="Log" onClick={this.logMessage.bind(this)} />
    );
  }
}
```
- Approach 3: Use Arrow Function in Render
```js
class HelloWorld extends React.Component {
  constructor(props) {
    super(props);
    this.state = { message: 'Hi' };
  }

  logMessage() {
    // This works because of the arrow function in render below.
    console.log(this.state.message);
  }

  render() {
    return (
      <input type="button" value="Log" onClick={() => this.logMessage()} />
    );
  }
}
```
- Approach 4: Bind in Constructor
```js
class HelloWorld extends React.Component {
  constructor(props) {
    super(props);
    this.state = { message: 'Hi' };
    this.logMessage = this.logMessage.bind(this);
  }

  logMessage() {
    // This works because of the bind in the constructor above.
    console.log(this.state.message);
  }

  render() {
    return (
      <input type="button" value="Log" onClick={this.logMessage} />
    );
  }
}
```
- Approach 5: Arrow Function in Class Property
```js
class HelloWorld extends React.Component {
  // Note that state is a property,
  // so no constructor is needed in this case.
  state = {
    message: 'Hi'
  };

  logMessage = () => {
    // This works because arrow funcs adopt the this binding of the enclosing scope.
    console.log(this.state.message);
  };

  render() {
    return (
      <input type="button" value="Log" onClick={this.logMessage} />
    );
  }
}
```
[5 Approaches for Handling `this`](https://medium.freecodecamp.org/react-binding-patterns-5-approaches-for-handling-this-92c651b5af56)

#### [Return: Express README](../README.md)
