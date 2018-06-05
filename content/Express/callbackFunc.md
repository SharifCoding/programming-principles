![Callback Function](https://vanilla-java.github.io/images/Request-Response.jpg)
## Request & Response (Callback Function)

___Express application makes use of a callback function whose parameters are request and
response objects.___
```js
app.get('/', function (req, res) { // --
})
```
<b>Request Object</b> - The request object represents the HTTP request and has properties for the request query string, parameters, body, HTTP headers, and so on.
<b>Response Object</b> - The response object represents the HTTP response that an Express app sends when it gets an HTTP request.

You can print req and res objects which provide lot of information related to HTTP request and response including cookies, sessions, URL etc.

#### [Return: Express README](../../README.md)
