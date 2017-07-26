+++
date = "2017-07-26T13:51:06-04:00"
title = "React Native"
tags = [
    "Javascript",
    "React",
    "React Native"
]
categories = [
    "Javascript",
    "React",
    "React Native"
]
menu = "main"
+++




At GRT, we recently built a React web client for a small educational startup.  Once this web app was feature complete, we decided to do a do a port to React Native as a learning experience and proof of concept.  We definitely learned some stuff.

**What is React Native?**

[React Native](https://facebook.github.io/react-native/) is a set of tools that lets you build *Native* Android and iOS apps using JavaScript and React. This is not a webapp run in some webview in a native wrapper.  The React Native code compiles down to a native executable.

**Why would you want to do this?**

So you can write a cross platform app that has the snappy, responsive feel of a native app without having to dive into actual native implementation.  Basically you want to write native apps in Javascript.

Ok, so let's say you have a React web app like we did, and you want to try porting it to React Native.

**First of all, go back in time and write the React Native implementation first.**

Just kidding... sort of.  

Here's the thing.  React for the web is much more forgiving and flexible than React Native.  React Native does not used HTML or CSS, so if you wrote CSS and have a bunch of HTML in your webapp, you're going to be spending some time rewriting.  However React for the web support styling using JS objects, so the port in the other direction is easy. Also let's say you're using a bunch of 3rd party UI modules in your app.  If you have this all figured out for React Native, you're going to have a pretty easy time finding modules with comperable APIs for the web.  The reverse is not likely to be the case right now.

**Abstract even MORE logic that you think.**

So part of the idea of porting your app to React Native is so you can share code right?  If your code is in a view, you're not sharing it.  Look how much logic you have in your `.jsx` files.  A ton, right?  All that has to be pulled out into modules if you want to maintain it in one place.  Think about this ahead of time.  If you're using Redux, you can think about this in terms of [Component and a Containter](http://redux.js.org/docs/basics/UsageWithReact.html#presentational-and-container-components).


**Do you even need a native app?**

One more thing we discovered is that the percieved perfomance on mobile of our React Native app was not superior enough to the web app to justify maintaining them both.  Depending on the level of interactivity in your UI a web app may offer suitable performance and user experience. 

**So what should you do?**

React Native is a great solution for writing cross platform mobile apps in Javascript, but there are meaningful enough differences from React that you'll want to plan carefully if you're planning on sharing code.  Maintaining multiple codebases always comes at a cost, so do some experiments and consider how much you have to gain from a native app before committing.

 