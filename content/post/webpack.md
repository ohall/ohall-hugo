+++
title = "Webpack: Rage to sage"
date = "2015-08-14T20:25:50-04:00"
tags = [
    "javascript",
    "webpack",
    "development"
]
categories = [
    "Development",
    "Tooling",
    "JavaScript"
]
menu = "main"
+++

If you're like me, your first encounter with Webpack was probably hostile. You're trying to learn some new technology like React, launching a demo project to see how it works and something is broken. You examine the build scripts and suddenly you're confronted with this arcane looking `webpack.config.js` file. You cruise over to the documentation for Webpack. It has many pages, none of them marked _TL;DR_. You hate reading documentation! This is not even what you were trying to do! You're yak shaving again! Curse you JS tooling cambrian explosion! Gahh!!

Exhale. Webpack is not that complicated, especially for simple work flows. It's becoming an integral part of the JS ecosystem and so it's worth sitting down and learning it. You can do this, just focus.

### TL;DR
 - Webpack is a module bundler like Browserify, but with better support for Node and React.
 - Webpack is not that hard.
 - Here's a simple example: [https://github.com/ohall/webpack-example](https://github.com/ohall/webpack-example).

### What is the point of Webpack?

Webpack is a module bundler. You may be familiar with `Browserify` which allows you to use the AMD (Asynchronous Module Definition) syntax (`var foo = require('bar');`) in your frontend code, much the same and you would in your Node applications. Basically this:

```js
// awesome is exported in another file
var wicked = require('awesome');
wicked();
```

These tools basically suck in all the JS files required by your app and concatenate them into one JS file that you can add to your app. This is WAY better that managing a bunch of script tags in your `index.html` or wherever. You can configure [loaders](http://webpack.github.io/docs/loaders.html) to do the same thing with other static files, like css and images.

![webpack](http://webpack.github.io/assets/what-is-webpack.png) 

### But why Webpack? Doesn't Browserify do this more simply?

There are [compelling](http://mattdesl.svbtle.com/browserify-vs-webpack) [arguments](http://blog.namangoel.com/browserify-vs-webpack-js-drama) for both [technologies](https://www.reddit.com/r/reactjs/comments/30at04/webpack_vs_browserify_whats_best_for_react/). One big arguement for Webpack is the ability to do [React Hot-loading](https://gaearon.github.io/react-hot-loader/) easily, speeding up dev time. But this post isn't about choosing between the two. For whatever reason, you're using Webpack now, DEAL WITH IT.

### I'm looking at webpack.config.js and I'm angry.
Whoa. It's cool. Look, let's start with a very simple example, so we can improve the signal to noise ratio. You can find a repo with this example here: [https://github.com/ohall/webpack-example](https://github.com/ohall/webpack-example) 

Let's say you have an `index.js` file;

```js
// index.js
var sweet = require('./sweet');
sweet();
```
 
That requires a sweet module `sweet.js`

```js
// sweet.js
module.exports = function () {
  window.onload = function () {
    var t = document.createTextNode('You did it! Sweet!');
    document.body.appendChild(t);
  }
};
```

We can set up our super simple `webpack.config.js` file will export a module with `index.js` as our entry file and output a file called `bundle.js`. Webpack figures out the rest. 


```js
module.exports = {
    entry: "./index.js",
    output: {
        path: __dirname,
        filename: "bundle.js"
    }
}
```
NOTE: `__dirname` is a [reference in Node for the currently executing directory.](https://nodejs.org/docs/latest/api/globals.html#globals_dirname)


Once you've installed Webpack globally,

```sh
npm install webpack -g
```

you can run `webpack` and create a `bundle.js` file that includes all the modules we need and use it in your HTML. [Run the example](https://github.com/ohall/webpack-example) to see what the bundle looks like.



```html
<!--index.html-->
<!doctype html>
<html>
    <script src="bundle.js"></script>
<body></body>
</html>
```

### Conclusion
There is SO much more to Webpack, that I'll dive into in the next post. For now though, you have enough to get you a footing in Webpack and start experimenting. JS tooling can be frustrating, especially when it feels like you have to learn a whole new build system every week. Don't despair! Start simple, take time to learn it and try to have fun.

<a hred