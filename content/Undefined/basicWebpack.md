![webpack](https://webpack.github.io/assets/what-is-webpack.png)
## What is Webpack?

___Webpack is a module bundler, that takes modules with dependencies and emits static assets representing those modules.___

With Webpack, you give a single path. The path to your entry point. This is typically `index.js` or `main.js`. Webpack will now investigate your application. It will figure out how everything is connected through require, import, etc. statements, url values in your CSS, href values in image tags, etc. It creates a complete dependency graph of all the assets your application needs to run. All of this just pointing to one single file.

An asset is a file. It being an image, css, less, json, js, jsx etc. And this file is a node in the dependency graph created by Webpack.

It is incredibly configurable, but to get started you only need to understand four Core Concepts:
- [Entry](#entry)
- [Output](#output)
- [Loaders](#loaders)
- [Plugins](#plugins)

#### Entry
An entry point indicates which module webpack should use to begin building out its internal dependency graph. After entering the entry point, webpack will figure out which other modules and libraries that entry point depends on (directly and indirectly).

Here’s the simplest example of entry configuration:
```js
// webpack.config.js

module.exports = {
  entry: './path/file.js'
};
```
#### Output
The output property tells webpack where to emit the bundles.  It also creates and how to name these files. You can configure this part by specifying a output field in your configuration.
```js
// webpack.config.js

const path = require('path');

module.exports = {
  entry: './path/file.js',
  output: {
    path: path.resolve(__dirname, 'dist'),
    filename: 'bundle.js'
  }
};
```
#### Loaders
Loaders enable webpack to process more than just JavaScript files. They give you the ability to leverage webpack’s bundling capabilities for all kinds of files by converting them to valid modules that webpack can process. Example of loaders is vue-loader, babel-loader, css-loader, etc.
```js
// webpack.config.js

const path = require('path');

const config = {
  entry: './path/file.js',
  output: {
    path: path.resolve(__dirname, 'dist'),
    filename: 'bundle.js'
  },
  module: {
    rules: [
      { test: /\.txt$/, use: 'raw-loader' }
    ]
  }
};

module.exports = config;
```
#### Plugins
While loaders are used to transform certain types of modules, plugins can be leveraged to perform a broader range of tasks. Plugins range from bundle optimization and minification all the way to defining environment-like variables.
```js
// webpack.config.js

const HtmlWebpackPlugin = require('html-webpack-plugin'); //installed via npm
const webpack = require('webpack'); //to access built-in plugins
const path = require('path');

const config = {
  entry: './path/file.js',
  output: {
    path: path.resolve(__dirname, 'dist'),
    filename: 'bundle.js'
  },
  module: {
    rules: [
      { test: /\.txt$/, use: 'raw-loader' }
    ]
  },
  plugins: [
    new webpack.optimize.UglifyJsPlugin(),
    new HtmlWebpackPlugin({template: './src/index.html'})
  ]
};

module.exports = config;
```

[webpack.js.org](http://webpack.js.org/)

#### [Return: Express README](../../README.md)
