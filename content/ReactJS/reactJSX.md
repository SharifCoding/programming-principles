![JSX](https://cdn-images-1.medium.com/max/1600/1*-ty7aZqH2of-rXpWYaoKPQ.png)

___JavaScript XML (JSX) is an XML syntax that constructs the markup in React components.___

## JSX Introduction
React works without JSX, but using JSX makes it easy to read and write the React components as well as structure them just like any other HTML element.

- JSX is a XML-like syntax extension to ECMAScript without any defined semantics”
- JSX is a markup language (like HTML) which allows us to define React components in a declarative way.
- It is also possible to make use of JavaScript code within JSX blocks by encapsulating them in curly braces.
- () denotes a JSX block.
- {} denotes a JavaScript snippet within JSX.
```js
{ const awesome = true; }
```

### React without/with JSX:
```js
// render without JSX
render: function(){
return(React.createElement("div",
                            null,
                            "Hello React World!"));
}
// render with JSX
render: function(){
  return <div>
    Hello React World
  </div>;
}
```

[Introducing JSX](https://reactjs.org/docs/introducing-jsx.html)

[Image Source](https://medium.com/modern-user-interfaces/dear-templating-sincerely-jsx-part-1-1df99c599001)

#### [Return: Express README](../../README.md)
