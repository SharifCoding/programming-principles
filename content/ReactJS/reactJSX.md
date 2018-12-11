![JSX](https://cdn-images-1.medium.com/max/1600/1*-ty7aZqH2of-rXpWYaoKPQ.png)

___JavaScript XML (JSX) is an XML syntax that constructs the markup in React components.___

## JSX Introduction
All of React components have a `render` function that specifies what the HTML output of our React component will be. <b>JavaScript eXtension</b>, or more commonly <b>JSX</b>, is a React extension that allows us to write JavaScript that _looks like_ HTML. React works without JSX, but using JSX makes it easy to read and write the React components as well as structure them just like any other HTML element.

- JSX is a XML-like syntax extension to ECMAScript without any defined semantics.
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
Because JSX is JavaScript, we can't use JavaScript reserved words. This includes words like `class` and `for`.

React gives us the attribute `className`. We use it in `HelloWorld` to set the `large` class on our `h1` tag. There are a few other attributes, such as the `for` attribute on a label that React translates into `htmlFor` as `for` is also a reserved word. We'll look at these when we start using them.

If we want to write pure JavaScript instead of rely on a JSX compiler, we can just write the `React.createElement()` function and not worry about the layer of abstraction. But we like JSX. It's especially more readable with complex components. Consider the following JSX:
```javascript
<div>
  <img src="profile.jpg" alt="Profile photo" />
  <h1>Welcome back Ari</h1>
</div>
```
The JavaScript delivered to the browser will look like this:
```javascript
React.createElement("div", null,
  React.createElement("img", {src: "profile.jpg", alt: "Profile photo"}),
  React.createElement("h1", null, "Welcome back Ari")
);
```
Again, while you can skip JSX and write the latter directly, the JSX syntax is well-suited for representing nested HTML elements.

#### Further Reading
- [Introducing JSX](https://reactjs.org/docs/introducing-jsx.html) - An XML syntax that constructs the markup in React components.
- [JavaScript ES6 — write less, do more](https://medium.freecodecamp.org/write-less-do-more-with-javascript-es6-5fd4a8e50ee2) - JavaScript ES6 brings new syntax and new awesome features to make your code more modern and more readable.

[Image Source](https://medium.com/modern-user-interfaces/dear-templating-sincerely-jsx-part-1-1df99c599001)

#### [Return: Express README](../../README.md)
