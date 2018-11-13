# Changing The DOM with DevTools and JavaScript

## Learning Goals

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
on "View", then select "Developer", then "Developer Tools." This will open the
Google Developer Tools. Click on the "Elements" tab. Here we have the DOM
representation of the HTML source the browser loaded.

### Select an Element With Chrome DevTools

Scroll through the Elements panel. You will see what looks like HTML. There are `head` tags, `body` tags, `div`s, etc.

![delete-header](http://web-dev-readme-photos.s3.amazonaws.com/js/header-click.png)

Now, from inside the developer console, locate and click on the element that
says `header`. You will notice that the `header` section of the webpage is
highlighted. You've now selected an element with the DevTools.

### Delete an Element with Chrome DevTools

![deleted-header](http://web-dev-readme-photos.s3.amazonaws.com/js/deleted-header.png)

Press the delete button on your keyboard. The element will vanish from the
browser's rendered page.

### Demonstrate That the Source is Not Changed When the DOM Is

View the page source. From this web page, look at the Chrome menu bar at the top
of the page. Click on "View", then select "Developer", then "View Source." You
will see the that the HTML is just as it always was, with a header tag and lots
of other elements inside.

![html-source](https://s3.amazonaws.com/learn-verified/html-javascript-lesson.png)

The changes in the DOM do not affect the HTML file on the server. When you think
about it, that makes sense. If that were true then anyone could be changing
carefully-written HTML.

The HTML, which lives on the server, **is unchanged**.

Refresh the page by going to "View" and choosing "Reload this Page." You will be
reloading the DOM from the source. The `header` will come back.

### Demonstrate Opening the DevTools' JavaScript Console

We can do the exact same work we did by selecting elements and deleting them
with delete key in the DevTools with JavaScript. In DevTools, click the
**Console** tab.

At the bottom you will see a cursor. There, type the word `document` and press
"Enter." You'll get a `#document` returned. If you click the disclosure
triangle, you'll see that it's the exact HTML that you would find in the
**Elements** tab. 

_Note: `disclosure triangle` is the triangle that is on the left side of the
`#document`. It is hiding the HTML that wouldn't normally be shown. It is good
information to have if you wanted more details about what is going on behind
the scenes. Those triangles are standard for hiding more information throughout
Chrome DevTools. If you want to see more, feel free to click on the triangle!
You're not going to break anything._

Since `document` is an `object` which means that it has properties and `methods`
we can imagine that by calling `methods` on it, it can return DOM elements.
Let's find or `select` an element by speaking JavaScript with the DOM.

### Select an Element with JavaScript

In the **Console** type:

```javascript
  document.querySelector('header')
```

This will return something like this: `<header class="site-
header">...</header>`. Go ahead and click on that disclosure triangle to see
more. This is the DOM Node, a JavaScript `object`. This means that it, in turn,
can have methods called on it! Let's save our header to a `variable`.

```javascript
  var headerObj = document.querySelector('header')
```

### Delete an Element with JavaScript

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

This is called method chaining. Since the call of `querySelector()` to the
document object returned a header object which supported a method called
`remove()`, we used dot-notation to chain the calls.

### Demonstrate That the Source is Not Changed When the DOM Is

Follow the same process we followed earlier to verify that the source has not
changed. To restore it, simply refresh the page (i.e. reload the DOM).

## Conclusion

DOM programming is using JavaScript to:

1. Ask the DOM to find or `select` an HTML element or elements in the rendered page
2. Remove the selected elements and/or insert a new element
3. Adjust a property of the selected element(s)

In this lesson you just did all that stuff! Learning to duplicate what you can
do in DevTools with JavaScript **is** DOM programming. The next lessons are
going to give you `methods` for selecting elements and changing them, but you
just changed the DOM. High fives are in order.
