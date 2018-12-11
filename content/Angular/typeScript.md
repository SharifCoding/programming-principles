![typeScript](https://camo.githubusercontent.com/065b4afb75b7589e814c57603f641ed42ddf01bd/687474703a2f2f616c6578616e6465722e686f6c6272656963682e6f72672f636f6e74656e742f696d616765732f323031362f30312f747970657363726970742d6573362d6573352e706e67)
## TypeScript

___TypeScript is described as a strict superset of JavaScript, which adds optional static typing and class-based object-oriented programming aligned with ECMAScript 6 standard proposal..___

Typescript brings to the world of JavaScript the benefits of statically typed languages such as:
- <b>Object-oriented paradigm</b> – Typescript brings the classes and interfaces to JavaScript what gives developers ability to write more object-oriented applications.
- <b>Type system</b> – Type checking can enhance workflow and enables tons of IDE features, such as a listing of members, parameter info or viewing quick documentation. Type checking is very useful while refactoring and it can catch mismatches in types or structure problems before an application runs in the browser.

Typescript is a superset of JavaScript meaning that every valid JavaScript program is also valid in Typescript. Therefore, developers can use the third-party libraries which are often written in JavaScript and applications very often depend on them. The fact that Typescript is a superset of JavaScript also has downsides. It does not eliminate weaknesses of JavaScript. It just offers the better way how to solve the same problem. The developer still can decide to write old-fashion code with all vulnerabilities and do not use all features of TypeScript.

### [Comparison TypeScript and JavaScript](http://www.typescriptlang.org/play/)
```js
// TypeScript
class Greeter {
    greeting: string;
    constructor(message: string) {
        this.greeting = message;
    }
    greet() {
        return "Hello, " + this.greeting;
    }
}

let greeter = new Greeter("world");

let button = document.createElement('button');
button.textContent = "Say Hello";
button.onclick = function() {
    alert(greeter.greet());
}

document.body.appendChild(button);
```

```js
// JavaScript ES5
var Greeter = (function () {
    function Greeter(message) {
        this.greeting = message;
    }
    Greeter.prototype.greet = function () {
        return "Hello, " + this.greeting;
    };
    return Greeter;
}());
var greeter = new Greeter("world");
var button = document.createElement('button');
button.textContent = "Say Hello";
button.onclick = function () {
    alert(greeter.greet());
};
document.body.appendChild(button);
```
#### Further Reading
- [TypeScript — JavaScript with superpowers](https://medium.freecodecamp.org/typescript-javascript-with-super-powers-a333b0fcabc9) - TypeScript is a typed superset of JavaScript that complies to plain JavaScript.

#### [Return: Express README](../../README.md)
