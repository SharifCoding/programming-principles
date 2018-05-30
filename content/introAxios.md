```css
axios.request(config)
axios.get(url[, config])
axios.delete(url[, config])
axios.head(url[, config])
axios.options(url[, config])
axios.post(url[, data[, config]])
axios.put(url[, data[, config]])
axios.patch(url[, data[, config]])
```

## Use Axios as Your HTTP Client

___Axios is a promise-based HTTP client that works both in the browser and in a node.js environment. It provides a single API for dealing with Http Requests and node’s http interface.___

Axios is promise-based and thus we can take advantage of async and await for more readable asynchronous code. We can also intercept and cancel requests, and there’s built-in client side protection against cross site request forgery. But the best part about Axios? The easy to use API!

Performing requests becomes trivial. In this example, performing requests to GitHub’s API:
```js
// Performing a GET request
axios.get('https://api.github.com/users/' + username)
  .then(function(response){
    console.log(response.data); // ex.: { user: 'Your User'}
    console.log(response.status); // ex.: 200
  });  

// Performing a POST request
axios.post('/save', { firstName: 'Marlon', lastName: 'Bernardes' })
  .then(function(response){
    console.log('saved successfully')
  });
```
Besides `post` and `get`, there are also methods named after the http methods `delete`, `head`, `put` and `patch`. The methods `post`, `put` and `patch` require a parameter containing the data to be sent.

To execute multiple requests in parallel, simply provide an array argument to axios.all. When all requests are complete, you’ll receive an array containing the response objects in the same order they were sent. Alternatively you can use axios.spread to spread the array into multiple arguments.
```js
// Requests will be executed in parallel...
axios.all([
    axios.get('https://api.github.com/users/codeheaven-io');
    axios.get('https://api.github.com/users/codeheaven-io/repos')
  ])
  .then(axios.spread(function (userResponse, reposResponse) {
    //... but this callback will be executed only when both requests are complete.
    console.log('User', userResponse.data);
    console.log('Repositories', reposResponse.data);
  }));
```
[axios](https://github.com/axios/axios)

#### [Return: Express README](../README.md)
