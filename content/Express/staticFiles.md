![Static Files](https://alligator.io/images/nodejs/serving-static-files-in-express.png)
## Serving Static Files

___Express provides a built-in middleware express.static to serve static files, such as images, CSS,
JavaScript etc.___

You simply needs to pass the name of the directory where you keep your static assets, to the express.static middleware to start serving the files directly. For example, if you keep your images, CSS, and JavaScript files in a directory named public, you can do this:
```js
// accessing to image path public/images/logo.png
var express = require("express");
var path = require("path");
var http = require("http");

var app = express();
// sets up the public path, using Node’s path module
var publicPath = path.resolve(__dirname, "public");
// sends static files from the publicPath directory
app.use(express.static(publicPath));

app.use(function(request, response) {
  response.writeHead(200, { "Content-Type": "text/plain" });
  response.end("Looks like you didn't find a static file.");
});

http.createServer(app).listen(3000);
```
Now, any file in the public directory will be shown. You can put anything in there that you please and the server will send it. If no matching file exists in the public folder, it’ll go on to the next middleware, and say “Looks like you didn’t find a static file.” If a matching file is found, express.static will send it off and stop the middleware chain.


#### [Return: Express README](../../README.md)
