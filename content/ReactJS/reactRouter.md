![reactRoute](https://cdn-images-1.medium.com/max/2000/1*eQLe7T33KNr82vcT378oPQ.jpeg)
## React Routers

___The routes are just components that get rendered to the screen when the app is running.___

React Router is the standard routing library for React. When you need to navigate through a React application with multiple views, you’ll need a router to manage the URLs. React Router does that, keeping your application UI and the URL in sync.

The React Router library comprises three packages:
- <b>react-router</b> - core package for the router, whereas the other two are environment specific.
- <b>react-router-dom</b> - for building a website.
- <b>react-router-native</b> - mobile app development environment using React Native.

#### React Router Basics
Here’s an example of how our routes will look:
```js
<Router>
  <Route exact path="/" component={Home}/>
  <Route path="/category" component={Category}/>
  <Route path="/login" component={Login}/>
  <Route path="/products" component={Products}/>
</Router>
```
You need a router component and several route components to set up a basic route as exemplified above. There are two types of routers from the React Router API:
- `<BrowserRouter>` - more popular because it uses the HTML5 History API to keep track of your router history.
- `<HashRouter>` - uses the hash portion of the URL (`window.location.hash`) to remember things.

The primary difference between them is evident in the URLs that they create:
```
// <BrowserRouter>
http://example.com/about

// <HashRouter>
http://example.com/#/about
```
If you intend to support legacy browsers, you should stick with `<HashRouter>`.

#### Further Reading
- [Routing React Apps: The Complete Guide](https://scotch.io/tutorials/routing-react-apps-the-complete-guide) - Full fleshed single page applications with React harnessing the powers of routing.

[Image Source](https://blog.cloudboost.io/use-react-router-v4-for-applications-d8346134db6c)

#### [Return: Express README](../../README.md)
