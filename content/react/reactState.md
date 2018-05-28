![Class](https://cms-assets.tutsplus.com/uploads/users/1795/posts/29541/image/Stateful-vs-Stateless-Component-Tutorial-Component-with-prop.jpg)

___The heart of every React component is its “state”, an object that determines how that component renders & behaves.___

#### Stateless/Stateful React Components

Example of a stateless component:
```js
var React = require('react');

var Header = React.createClass({
    render: function() {
        return(
            <img src={'mypicture.png'} />
        );
    }
});

module.exports = Header;
```
Example of a stateful component:
```js
var React = require('react');

var Header = React.createClass({

    getInitialState: function() {
        return {
            someVariable: "I remember something"
        };
    },

    render: function() {
        return(
            <img src={'mypicture.png'} />
        );
    }
});

module.exports = Header;
```

[Image Source](https://code.tutsplus.com/tutorials/stateful-vs-stateless-functional-components-in-react--cms-29541)

#### [Return: Express README](../../README.md)
