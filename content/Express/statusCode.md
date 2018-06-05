![Status Code](https://codeteddycom.files.wordpress.com/2017/06/statuscode.png?w=1109)
## HTTP Status Code
___All responses from an HTTP server come with an associated status code. The most common among them is 200, the code for a successful request.___

The data sent by an HTTP server in response to a request is called an HTTP response message. It is composed of a status code, headers, and optional associated data, which is technically referred to as the body of the message.

The body is presented to the user as plain text, rendered HTML, image, file download, and so on. The status code and the headers are hidden from a regular user, but the browser requires them to process the body appropriately.

<b>1xx</b> - The 1xx series of status codes is classified as Informational, and is used for conveying provisional response from the server.
<b>2xx</b> - The 2xx series of status codes is classified as Success, and is used for conveying a successful request for a resource on the server.
<b>3xx</b> - The 3xx series of status codes is classified as Redirection, and is used for information by the user agent about taking additional action to retrieve the requested resource.
<b>4xx</b> - The 4xx series of status codes is classified as Client Error, and is used for informing the user agent of its erroneous requests to the server.
<b>5xx</b> - The 5xx series of status codes is classified as Server Error, and is used for informing the user agent that the server has encountered an error because of which the request was not fulfilled.

#### [Return: Express README](../../README.md)
