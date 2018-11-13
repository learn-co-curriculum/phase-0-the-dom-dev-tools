# Changing The DOM With DevTools and JavaScript

## Problem Statement

1. Demonstrate viewing the DOM through Chrome DevTools
2. Select an element with Chrome DevTools
3. Delete an element with Chrome DevTools
4. Demonstrate that the source is not changed when the DOM is
5. Demonstrate opening the DevTools' JavaScript console
5. Select an element with JavaScript
6. Delete an element with JavaScript
7. Demonstrate that the source is not changed when the DOM is

## Introduction
In this lab, we're going to change the DOM in two ways. First, we'll use
Chrome's Developer Tools ("DevTools") to remove an element from the DOM. Then
we'll use the DevTools' JavaScript console to run JavaScript that does the same
thing.


## Instructions
### Demonstrate Viewing the DOM Through Chrome DevTools

![opening-console](https://s3.amazonaws.com/learn-verified/opening-console.gif)

From this web page, look at the Chrome menu bar at the top of the page. Click
on "View", then select "Developer", then "Developer Tools". This will open the
Google Developer Tools. Click on the "Elements" tab. Here we have the DOM
representation of the HTML source the browser loaded.

### Select an Element With Chrome DevTools

Scroll through the Elements panel

You will see what looks like HTML.  There are head tags, body tags, divs, etc.

![delete-header](http://web-dev-readme-photos.s3.amazonaws.com/js/header-click.png)

Now from inside the developer console, locate and click on the element that says `header`. You will notice that the `header` section of the webpage is highlighted. You've now selected an element with the DevTools.

### Delete an Element With Chrome DevTools

![deleted-header](http://web-dev-readme-photos.s3.amazonaws.com/js/deleted-header.png)

Press the delete button on your keyboard. The element will vanish from the
browser's rendered page.

### Demonstrate That the Source is Not Changed When the DOM is

View the page source. Right click (or two fingers click on the mac) on the
lesson page in the browser and select "View Page Source." You will see the that
the HTML is just as it always was, with a header tag and lots of other elements
inside.

![html-source](https://s3.amazonaws.com/learn-verified/html-javascript-lesson.png)

The changes in the DOM do not affect the HTML file on the server. When you
think about it, that seems silly. If that were true then anyone with DevTools
could be mucking around with your carefully-written HTML.

The HTML, which lives on the server, **is unchanged**.

Refresh the page and reload the DOM _from the source_. The `header` should come
back.

### Demonstrate opening the DevTools' JavaScript console

We can do the _exact same_ work we did by selecting elements and deleting them
with delete key in the DevTools, with JavaScript. In DevTools, click the
**Console** tab.

At the bottom you will see a cursor. There, type the word `document` and press
"Enter." You'll get a `#document` returned. If you click the disclosure
triangle, you'll see that it's the exact HTML that you would find in the
**Elements** tab. Since `document` is an _object_ which means that it has
_properties_ and _methods_ we can imagine that by calling _methods_ on it, it
can _return_ DOM elements. Let's find or select an element by speaking
JavaScript with our friend, the DOM.

### Select an Element With JavaScript

In the **Console** type:

```javascript
  document.querySelector('header')
```

This will return something like this: `<header class="site-
header">...</header>`. Go ahead and click on that disclosure triangle to see
more. This is the DOM Node, a JavaScript _object_. This means that it, in turn,
can have methods called on it! Let's save our header to a _variable_.

```javascript
  var headerObj = document.querySelector('header')
```

### Delete an Element With JavaScript

Now type:

```javascript
  headerObj.remove()
```

The header is gone! 

If you refresh the page to get the `header` back, you could also try for some
slightly advanced JavaScript:

```javascript
  document.querySelector('header').remove()
```

This is called _method chaining_. Since the call of `querySelector()` to the
document _object_ "returned" a header object which supported a method called
`remove()`, we could use dot-notation to "chain" the calls.

### Demonstrate That the Source is Not Changed When the DOM is

Follow the same process we followed earlier to verify that the source has not
changed. Like before, to restore it, simply refresh the page i.e. reload the
DOM.

## Conclusion

DOM programming is using JavaScript to:

1. Ask the DOM to find or `select` an HTML element or elements in the rendered page
2. Remove the selected elements and/or insert a new element
3. Adjust a property of the selected element(s)


In this lesson you just did all that stuff! Learning to duplicate what you can
do in DevTools with JavaScript **is** DOM programming. The next lessons are
going to give you `methods` for selecting elements and changing them, but you
just changed the DOM. High fives are in order.
