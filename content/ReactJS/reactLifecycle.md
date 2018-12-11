![reactLifecyle](https://cdn-images-1.medium.com/max/2000/1*sn-ftowp0_VVRbeUAFECMA.png)
## React Render Lifecycle

___React enables to create components by invoking the React.createClass() method which expects a render method and triggers a lifecycle that can be hooked into via a number of so called lifecycle methods.___

To get a clear idea of the lifecycle we will need to differentiate between the initial creation phase, where the component is created, and state and props changes triggered updates as well as the component unmoutings phase.

The React component goes through the following phases;
- [Initialization](./reactState.md) - In this phase the React component prepares for the upcoming tough journey, by setting up the initial states and default props.
- [Mounting](./reactMounting.md) - After preparing with basic needs, state and props, our React Component is ready to mount in the browser DOM. This phase gives hook methods for before and after mounting of components.
- [Updation](./reactUpdating.md) - This phase starts when the react component has taken birth on the browser and grows by receiving new updates. The component can be updated by two ways, sending new props or updating the state.
- [Unmounting](./reactUnmounting.md) - In this phase, the component is not needed and the component will get unmounted from the DOM.

#### Further Reading
- [ReactJs component lifecycle methods](https://hackernoon.com/reactjs-component-lifecycle-methods-a-deep-dive-38275d9d13c0) - The lifecycle methods are various methods which are invoked at different phases of the lifecycle of a component.
- [React lifecycle code example](https://plnkr.co/edit/0cN0tu?p=preview) - Understanding the React Component Lifecycle.

#### [Return: Express README](../../README.md)
