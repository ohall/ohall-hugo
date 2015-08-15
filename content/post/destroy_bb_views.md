+++
date = "2014-12-01"
title = "Destroying BackboneJS Views"
tags = [
    "javascript",
    "development"
]
categories = [
    "Development",
    "JavaScript",
]
menu = "main"
+++


If you've spent much time using Backbone views, you've invariable encountered the situation where you want to get rid of a view, but some part of it keeps hanging around. Be it DOM elements or event listeners.  Your new view might be being appended to the old one, or you're seeing duplicated events. What you really need is to destroy that old view once and for all.

The easiest way to do this is by adding some kind of destroy() function to your view.

Here's how I do it:

```js
  Backbone.View.extend({
      //some other view stuff here...
      destroy: function () {
          this.undelegateEvents();
          this.$el.removeData().unbind();
          
          this.remove();
          //OR
          this.$el.empty();
      }
  });
```

Let's break this down.

__First__ we want to make sure we're removing all delegated events (the ones in the `events:{"event selector": "callback"}` hash). We do this so we can avoid memory leaks and not have mystery bindings that will fire unexpectedly later on. `undelegateEvents()` is a Backbone.View prototype function that removes the view's delegated events. Simple.

__Next__ we want to cleanup any data in the view object that is hanging around and unbind any events that we bound outside the events hash. jQuery provides a removeData() function that allows us to to do that. 

You may also have bound event listeners to your view chain `unbind()` with no arguments to remove all previously-attached event handlers from your $el.
`this.$el.removeData().unbind();`
 

__Now you may want to do one of two things here.__ You may want to remove your view element completely OR you just want to remove any child elements you've appended to it during it's life. The latter would be appropriate if, for example, you've set the $el of your view to be some DOM element that should remain after your view behavior is complete

In the former case, `this.remove()` will obliterate your view element and it's children from the DOM.

In the later case, `this.$el.empty()` will remove all child elements.

As you can see, it's not especially difficult to clean up your view, but you do have to do it.  As with many things in the unopinionated world of BackboneJS you have to roll your own solution. 

 

Check out [this fiddle](http://jsfiddle.net/oakley349/caqLx10x/) if you want to fool around with my solution.

<iframe width="100%" height="300" src="//jsfiddle.net/oakley349/caqLx10x/embedded/" allowfullscreen="allowfullscreen" frameborder="0"></iframe> 
