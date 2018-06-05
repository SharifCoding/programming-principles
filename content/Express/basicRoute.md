![Basic Routing](https://mdn.mozillademos.org/files/14456/MVC%20Express.png)
## Basic Routing
___Routing refers to determining how an application responds to a client request to a particular endpoint, which is a URI orpath and a specific HTTP request method GET, POST, and so on.___

Routing is a way to map requests to specific handlers depending on their URL and HTTP verb. You could imagine having a homepage and an about page and a 404 page. Routing can do all of this.
#### Express routing example
```js
// This responds with "Hello World" on the homepage
app.get('/', function (req, res) {
  console.log("Got a GET request for the homepage");
  res.send('Hello GET');
})
// This responds a POST request for the homepage
app.post('/', function (req, res) {
  console.log("Got a POST request for the homepage");
  res.send('Hello POST');
})
// This responds a DELETE request for the /del_user page.
app.delete('/del_user', function (req, res) {
  console.log("Got a DELETE request for /del_user");
  res.send('Hello DELETE');
})
// This responds a GET request for the /list_user page.
app.get('/list_user', function (req, res) {
  console.log("Got a GET request for /list_user");
  res.send('Page Listing');
})
// This responds a GET request for abcd, abxcd, ab123cd, and so on
app.get('/ab*cd', function(req, res) {
  console.log("Got a GET request for /ab*cd");
  res.send('Page Pattern Match');
})
```
#### Grabbing data from routes
```js
// specifies that the "hello" part of the route is fixed
app.get("/hello/:who", function(request, response) {
  // req.params has a property called who.
  response.end("Hello, " + request.params.who + ".");
  // Fun fact: this has some security issues, which we’ll get to!
});
```
It’s no coincidence that this who is the specified part in the first route. Express will pull the value from the incoming URL and set it to the name you specify. Restart your server and visit `localhost:3000/hello/earth` for the following message: `Hello, earth.` Note that this won’t work if you add something after the slash. For example, `localhost:3000/hello/entire/earth` will give a 404 error.
#### [Return: Express README](../../README.md)
