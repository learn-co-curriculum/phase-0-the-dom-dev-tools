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

We've read that updating the DOM will update the browser's rendered page. Let's
experience this now. We're going to change the DOM in two ways. First, we'll use
Chrome's Developer Tools ("DevTools") and our mouse to remove an element from
the DOM. Then we'll use the DevTools' JavaScript console to run JavaScript that
does the same thing.

## Instructions

### Demonstrate Viewing the DOM Through Chrome DevTools

![opening-console](https://s3.amazonaws.com/learn-verified/opening-console.gif)

From this web page, look at the Chrome menu bar at the top of the page. Click
on "View", then select "Developer", then "Developer Tools." This will open the
Google Developer Tools. Click on the "Elements" tab. Here we have the DOM
representation of the HTML source the browser loaded.

### Select an Element With Chrome DevTools

Scroll through the Elements panel. You will see some HTML: `head` tags, `body`
tags, `div`s, etc.

![delete-header](http://web-dev-readme-photos.s3.amazonaws.com/js/header-click.png)

Now, from inside the developer console, locate and click on the element that
says `header`. You will notice that the `header` section of the webpage is
highlighted. You've now selected an element with the DevTools.

### Delete an Element With Chrome DevTools

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
reloading the DOM _from the source_. The `header` will come back.

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

### Select an Element With JavaScript

In the **Console** type:

```javascript
  document.querySelector('header')
```

This will return something like this: `<header class="site-
header">...</header>`. Go ahead and click on that disclosure triangle to see
more. This is the DOM Node, a JavaScript `object`. This means that it, in turn,
can have methods called on it! This is called _method chaining_. Let's use
_method chaining_ to remove our node from the DOM.

### Delete an Element with JavaScript

Now type:

```javascript
  document.querySelector('header').remove()
```

The header is gone! We called `document.querySelector('header')` in order
to get the node onto which we _chained_ the call to `remove()`. We use
dot-notation to _chain_ the calls.

### Demonstrate That the Source is Not Changed When the DOM Is

Follow the same process we followed earlier to verify that the source has not
changed. To restore it, simply refresh the page (i.e. reload the DOM).

### Preview JavaScript Variables

Have you ever heard a celebrity or royalty refer to themselves in the third
person repeatedly:

"MC Egotrip is the greatest rapper ever to walk this earth. When
MC Egotrip is hungry, he likes grilled cheese sandwiches, but not too much
cheese or Gruy&egrave;re because MC Egotrip is mildly lactose intolerant."

And then you think "Please, use a pronoun. '_I_' would be a good start!"

In the same way our JavaScript code would be really annoying if we always
had to refer to a node by looking it up with `document.querySelector`. We'd
like to have JavaScript do that finding work finding the node _once_ and then
_save_ our ability to refer to that node. That's exactly what _variables_ do.
Just like pronouns in human communication, variables let us refer to
a calculation, a process, or a value by giving it a name. In the next lesson
we'll talk in depth about _variables_.

## Conclusion

DOM programming is using JavaScript to:

1. Ask the DOM to find or `select` an HTML element or elements in the rendered page
2. Remove the selected elements and/or insert a new element
3. Adjust a property of the selected element(s)

In this lesson you just did all that stuff! Learning to duplicate what you can
do in DevTools with JavaScript **is** DOM programming. The next lessons are
going to give you `methods` for selecting elements and changing them, but you
just changed the DOM. High fives are in order.

<p class='util--hide'>View <a href='https://learn.co/lessons/fewpjs-changing-the-dom-with-dev-tools-and-javascript'>Changing the DOM with DevTools and JavaScript</a> on Learn.co and start learning to code for free.</p>
