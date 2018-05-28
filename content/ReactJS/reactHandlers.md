![Handling](https://webjustify.com/wp-content/uploads/2018/04/event-handler.png)

___Handling events with React elements is very similar to handling events on DOM elements.___
#### Event Handling
Event handling only goal is intercepting various events (clicks, touches…) and triggering the associated callbacks that you, the programmer, coded. It’s the implementation that makes React’s event handling system stand out.

JSX elements can have event listeners, just like HTML elements can. You create an event listener by giving a JSX element a special attribute. Here's an example:
```js
<img onClick={myFunc} />
```
An event listener attribute's name should be something like onClick or onMouseOver: the word on, plus the type of event that you're listening for. An event listener attribute's value should be a function. The above example would only work if myFunc were a valid function that had been defined elsewhere:
```js
function myFunc() {
    alert('Make myFunc the pFunc...');
    } <img onClick={myFunc} />
```
Note that in HTML, event listener names are written in all lowercase, such as onclick or onmouseover. In JSX, event listener names are written in camelCase, such as onClick or onMouseOver.

[Image Source](http://webjustify.com/reactjs-events/)

#### [Return: Express README](../../README.md)
