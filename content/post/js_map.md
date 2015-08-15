+++
date = "2014-11-13T10:06:47-04:00"
title = "JS map()"
tags = [
    "javascript",    
    "underscore",
    "underscore",
    "development"
]
categories = [
    "OSX",
    "Bash",
    "Development"
]
+++

`map()` is an array utility function that you're probably either intimately familiar with or, like me, need to learn.

In a nutshell, `map()` creates a new array out of the results of calling a given function on every element on the array on which it's called.

There are implementations of map() in [native JS](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map), [jQuery](http://api.jquery.com/jquery.map/) and [UnderscoreJS](http://underscorejs.org/#map).  All other things being equal, [__Underscore's__ version is the most performant](http://jsperf.com/map-underscore-vs-jquery/2). 


#### map() is a 'collection function', meaning it works on either Arrays or Objects 

If our collection is an __Array__, map() will put each value through a transformational function, passing the value at each index to the array to the callback function as the first parameter, the index as the second and the whole array as the third. 
    
```sh
var collection = [1, 2, 3];

_.map(collection, function(val, index, array){ return num * 3; });

// returns array -> [3, 6, 9]
```

Similarly, if our collection is an __Object__, map() will pass the the value and key if each attribute, as well as the whole object.  

```sh
var collection = {one: 1, two: 2, three: 3};

_.map(collection, function(val, key, object){ return num * 3; });

// returns array -> [3, 6, 9]
```
