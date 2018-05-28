## Updating Lifecycle Methods

___This phase starts when the react component has taken birth on the browser and grows by receiving new updates. The component can be updated by two ways, sending new props or updating the state.___

The first time that a component instance renders, it does not update. A component updates every time that it renders, starting with the second render.
There are four updating lifecycle methods:

- [componentWillReceiveProps](#componentWillReceiveProps)
- [shouldComponentUpdate](#shouldComponentUpdate)
- [componentWillUpdate](#componentWillUpdate)
- [render](./reactMounting.md#render)

Whenever a component instance updates, it automatically calls all four of these methods, in order.

#### componentWillReceiveProps
The first updating lifecycle method is called `componentWillReceiveProps`.
When a component instance updates, `componentWillReceiveProps` gets called before the rendering begins.
As one might expect, `componentWillReceiveProps` only gets called if the component will receive props:
```js
// componentWillReceiveProps will get called here:
ReactDOM.render( <Example prop="myVal" />, document.getElementById('app') );

// componentWillReceiveProps will NOT get called here:
ReactDOM.render( <Example />, document.getElementById('app') );
```
`componentWillReceiveProps` automatically gets passed one argument: an object called `nextProps`. `nextProps` is a preview of the upcoming props object that the component is about to receive.
On line 4, `nextProps.text` will evaluate to "Hello world".
```js
export class Example extends React.Component {
  componentWillReceiveProps(nextProps) {
    alert("Check out the new props.text that "
    	+ "I'm about to get:  " + nextProps.text);
  }
  render() {
    return <h1>{this.props.text}</h1>;
  }
}

// The first render won't trigger
// componentWillReceiveProps:
ReactDOM.render(
	<Example text="Hello world" />,
	document.getElementById('app')
);

// After the first render, 
// subsequent renders will trigger
// componentWillReceiveProps:
setTimeout(() => {
	ReactDOM.render(
		<Example text="Hello world" />,
		document.getElementById('app')
	);
}, 1000);
```
#### shouldComponentUpdate
The second updating lifecycle method is called `shouldComponentUpdate`.
When a component updates, `shouldComponentUpdate` gets called after `componentWillReceiveProps`, but still before the rendering begins.
`shouldComponentUpdate` should return either true or false.
If `shouldComponentUpdate` returns true, then nothing noticeable happens. But if `shouldComponentUpdate` returns false, then the component will not update! None of the remaining lifecycle methods for that updating period will be called, including `render`.
The best way to use `shouldComponentUpdate` is to have it return false only under certain conditions. If those conditions are met, then your component will not update.
`shouldComponentUpdate` automatically receives two arguments: `nextProps` and `nextState`. It's typical to compare `nextProps` and `nextState` to the current `this.props` and `this.state`, and use the results to decide what to do.
```js
export class Example extends React.Component {
  constructor(props) {
    super(props);

    this.state = { subtext: 'Put me in an <h2> please.' };
  }
  shouldComponentUpdate(nextProps, nextState) {
    if ((this.props.text == nextProps.text) && 
      (this.state.subtext == nextState.subtext)) {
      alert("Props and state haven't changed, so I'm not gonna update!");
      return false;
    } else {
      alert("Okay fine I will update.")
      return true;
    }
  }
  render() {
    return (
      <div>
        <h1>{this.props.text}</h1>
        <h2>{this.state.subtext}</h2>
      </div>
    );
  }
}
```
#### componentWillUpdate
The third updating lifecycle method is `componentWillUpdate`.
`componentWillUpdate` gets called in between `shouldComponentUpdate` and `render`.
`componentWillUpdate` receives two arguments: `nextProps` and `nextState`.
You cannot call `this.setState` from the body of `componentWillUpdate`.
The main purpose of `componentWillUpdate` is to interact with things outside of the React architecture. If you need to do non-React setup before a component renders, such as checking the window size or interacting with an API, then `componentWillUpdate` is a good place to do that.
```js
export class Example extends React.Component {
  componentWillUpdate(nextProps, nextState) {
    alert('Component is about to update!  Any second now!');
  }
  render() {
    return <h1>Hello world</h1>;
  }
}
```

#### [Return: React Render Lifecyle](./reactLifecycle.md)

#### [Return: Express README](../../README.md)

