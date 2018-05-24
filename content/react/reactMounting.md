## Mounting Lifecycle Methods

___After preparing with basic needs, state and props, our React Component is ready to mount in the browser DOM. This phase gives hook methods for before and after mounting of components.___

A component "mounts" when it renders for the first time. This is when mounting lifecycle methods get called.
There are three mounting lifecycle methods:

- [componentWillMount](#componentWillMount)
- [render](#render)
- [componentDidMount](#componentDidMount)

When a component mounts, it automatically calls these three methods, in order.

#### componentWillMount
The first mounting lifecycle method is called `componentWillMount`.
When a component renders for the first time, `componentWillMount` gets called right before `render`.
Look at `Example.js`, and follow these steps:
1.	On lines 14-17, `<Example />` is rendered for the first time. `<Example />`'s mounting period begins.
2.	`<Example />` calls the first mounting lifecycle method, componentWillMount.
3.	componentWillMount executes, and an alert appears on the screen. (lines 5-7)
4.	After componentWillMount has finished, `<Example />` calls the second mounting lifecycle method: render.
5.	`<h1>Hello world</h1>` appears on the screen (lines 9-11)
6.	Two seconds later, `<Example />` renders again (lines 20-22).componentWillMount does NOT get called, because mounting lifecycle events only execute the first time that a component renders.

You can call `this.setState` from within `componentWillMount`.

```js
import React from 'react';
import ReactDOM from 'react-dom';

export class Example extends React.Component {
  componentWillMount() {
    alert('component is about to mount!');
  }

  render() {
    return <h1>Hello world</h1>;
  }
}

ReactDOM.render(
  <Example />,
  document.getElementById('app')
);

setTimeout(() => {
  ReactDOM.render(
    <Example />,
    document.getElementById('app')
  );
}, 2000);
```
#### render
`render` is a lifecycle method! Whenever a component mounts, `componentWillMount` is called first, followed by `render`, followed by `componentDidMount`.
`render` belongs to two categories: mounting lifecycle methods, and updating lifecycle methods.

#### componentDidMount
When a component renders for the first time, `componentDidMount` gets called right afterthe HTML from render has finished loading.
If your React app uses AJAX to fetch initial data from an API, then `componentDidMount` is the place to make that AJAX call. More generally, `componentDidMount` is a good place to connect a React app to external applications, such as web APIs or JavaScript frameworks. `componentDidMount` is also the place to set timers using `setTimeout` or `setInterval`.

```js
import React from 'react';

export class Example extends React.Component {
  componentDidMount() {
    alert('component just finished mounting!');
  }

  render() {
    return <h1>Hello world</h1>;
  }
}
```

#### [Return: React Render Lifecyle](./reactLifecycle.md)
