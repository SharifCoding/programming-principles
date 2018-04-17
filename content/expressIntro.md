![express logo](../img/expressJS.png)

___Express is a (relatively) lightweight server-side JavaScript framework that runs on a Node.js server.___
## ExpressJS Introduction

### What is Node?
- Node.js is a webserver that operates on the V8 Google Chrome JavaScript runtime, allowing you to write server-side code in JavaScript.
- Node.js provides the ability to handle requests and issue responses.
- It is fast.
- It is fast largely because it is asynchronous, meaning code can run in parallel without "blocking" the call stack (the list of other concurrent commands).

### NPM and NPM Init
- NPM stands for Node Package Manager, and is a tool that allows us to easily download community-built Node packages.
- Initialize new Node project with NPM: `npm init`.
- Install NPM packages: `npm install --save express`.
- NPM works with package.json, which is a list of project information and dependencies that can be installed on other computers and servers.

### What is Node Good For?
- Node really shines when it comes to heavy input-output type operations.
- Realtime services like chat applications or conferencing platforms benefit from using Node.
- APIs are also input/output heavy, and they also tend to work with JavaScript out of the box (think JSON). What better platform than Node?

### Express JS
- Express is a framework built on top of Node.js that makes development of web servers more intuitive and quicker.
- Express allows us to easily set up routes that will trigger actions such as rendering pages or returning JSON.

### Express ___'Hello World'___ example:
```js
const express = require('express');

const app = express();

app.get('/', (req, res) => {
  res.send('Hello world');
});

app.listen(3000, () => {
  console.log('App running on port 3000');
});
```
First we require() the express module and create an Express application. This object, which is traditionally named app, has methods for routing HTTP requests, configuring middleware, rendering HTML views, registering a template engine, and modifying application settings that control how the application behaves (e.g. the environment mode, whether route definitions are case sensitive, etc.)

The middle part of the code (the three lines starting with `app.get`) shows a route definition. The app.get() method specifies a callback function that will be invoked whenever there is an HTTP GET request with a path (`'/'`) relative to the site root. The callback function takes a request and a response object as arguments, and simply calls send() on the response to return the string `'Hello world'`.

The final block starts up the server on port `3000` and prints a log comment to the console. With the server running, you could go to localhost:3000 in your browser to see the example response returned.

[Express](http://expressjs.com/)

### [Return: Express README](../README.md)
