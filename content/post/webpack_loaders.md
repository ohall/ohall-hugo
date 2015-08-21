+++
date = "2015-08-20T09:00:59-04:00"
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
title = "Webpack Loaders"
+++

Start with the <a href="/post/webpack">webpack basics<a>

## What is a loader?

A loader is [basically a preprocessor](http://webpack.github.io/docs/loaders.html). It's how you let webpack know that you'd like to transform a module in some specified way. For example, let's say you are writing your code in [ES6](https://hacks.mozilla.org/category/es6-in-depth/) and you'd like webpack to process that into ES5 so the browser can parse it.  You'd define a loader for [babel](https://babeljs.io/) that looks for `.js` files being required and then runs them through babel before adding them to the [bundle](https://github.com/webpack/webpack/tree/master/examples/commonjs#jsoutputjs).

## Example, please
You can check out the working example here [repo here](https://github.com/ohall/webpack-loaders-example).

So here is our `index.js` with some cutting edge ECMAScript6 code.

```js
// look at this cool ES6 syntax!
import sweet from './sweet';

sweet();
```

let's run `webpack` and get our bundle on.

Oh no! Gruesome error!

```sh
ERROR in ./index.js
Module parse failed: /Users/ohall/Documents/projects/webpack-loaders-example/index.js Line 2: Unexpected reserved word
You may need an appropriate loader to handle this file type.
| // look at this cool ES6 syntax!
| import sweet from './sweet';
| 
| sweet();
```

We need to fix this by defining a loader in order to preprocess our ES6 stuff into palatable ES5.

Let's update our `webpack.config.js` like so.

```js
module.exports = {
  entry: "./index.js",
  output: {
    path: __dirname,
    filename: "bundle.js"
  },
  module: {
    loaders: [
      { test: /\.js$/, exclude: /node_modules/, loader: 'babel'}
    ]
  }
};
```


let's run `webpack` AGAIN!

__SCORE!__

```sh
Hash: 3e3bbd08bc6f0ce8543b
Version: webpack 1.11.0
Time: 430ms
    Asset     Size  Chunks             Chunk Names
bundle.js  1.96 kB       0  [emitted]  main
    + 2 hidden modules
```

Now our `bundle.js` is complete and looking right.

## Ok, so what just happened?

I added a `module` to our `webpack.config.js` with a `loaders` array.  Inside that array, I defined a babel loader.

```js
  module: {
    loaders: [
      { test: /\.js$/, exclude: /node_modules/, loader: 'babel'}
    ]
  }
```

__What the loader does is:__

1. Apply the test.  In this case, looking for files that end in `.js`
2. Exclude and files in the `node_modules` dir, bc that's not our concern.
3. Run the files that match our test through the loader we've specified, in this case, babel.

So what we have is our ES6 source being parsed by babel __before__ being added to our `bundle.js`.

Simple, right?

## What else can I use loaders for.

You can process anything.  Common use cases include `JSON`, `CSS`, static assets like images, dialects like CoffeeScript and Typescript.  The webpack wiki contains a [list of available loaders](https://github.com/webpack/docs/wiki/list-of-loaders) or you can [roll your own](http://webpack.github.io/docs/loaders.html#writing-a-loader).


