![react logo](../img/reactJS.png)

___React is a popular library used to create user interfaces. It was built at Facebook to address some of the challenges associated with large-scale, data-driven websites.___

## ReactJS Introduction

### What is React?
ReactJS tries to solve the problem from the View layer. It can very well be defined and used as the V in any of the MVC frameworks. It breaks down parts of the view in the Components. These components encompass both the logic to handle the display of view and the view itself. It can contain data that it uses to render the state of the app.

React is founded on the idea that DOM manipulation is an expensive operation and should be minimized. React solves this by giving the developer a virtual DOM to render to instead of the actual DOM. It finds difference between the real DOM and virtual DOM and conducts the minimum number of DOM operations required to achieve the new state.

### React ___'Hello World'___ example:
```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <title>Hello World</title>
      <!-- To create a component in React include the source as shown below: -->
      <script src="https://unpkg.com/react@16/umd/react.development.js"></script>
      <script src="https://unpkg.com/react-dom@16/umd/react-dom.development.js"></script>
      <script src="https://unpkg.com/babel-standalone@6.15.0/babel.min.js"></script>
  </head>
  <body>
    <div id="root"></div>
    <script type="text/babel">
      ReactDOM.render(
        <h1>Hello, world!</h1>,
        document.getElementById('root')
      );
    </script>
  </body>
</html>
```

[React](https://reactjs.org/)

#### [Return: Express README](../README.md)
