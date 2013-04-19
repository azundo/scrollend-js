scrollend-js
============

Adds the capability to configure and subscribe to a scrollEnd event.

Checks the scroll position every 100ms and fires subscriber functions if
scrolling has stopped. Doesn't attach to the scroll event as that produces
slow and jerky scrolling behaviour.

**Usage**

You must first create a ``ScrollEnd`` instance and then subscribe to it. Any
function that has subscribed is called when scrolling stops. ``ScrollEnd`` passes
the position of the top of the screen as an argument to all subscribers.

```javascript
var onScrollEnd = new ScrollEnd();

onScrollEnd.subscribe(function (scrollPosition) {
    console.log('You stopped scrolling at: ' + scrollPosition);
});
```

Functions can also be unsubscribed.

```javascript
var onScrollEnd = new ScrollEnd();

// subscribe
onScrollEnd.subscribe(myFunc);

// unsubscribe
onScrollEnd.unsubscribe(myFunc);
```

The ``sub`` and ``unsub`` functions are also aliased to ``subscribe`` and
``unsubscribe`` respectively.

**Configuration**

``ScrollEnd`` takes an options config options. Currently it only supports one
option, a ``checkInterval`` integer that specifies the interval in milliseconds to
check the scroll position for a stoppage. If not specified in options
``checkInterval`` defaults to 100.

```javascript

// check every 50ms instead of 100ms
onScrollEnd = new ScrollEnd({
    checkInterval: 50
});
```


**Demo**
A demo can be seen at http://azundo.github.io/scrollend-js/examples/.
