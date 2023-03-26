# JS HTML DOM

## 1 Document Object Model

![DOM Tree](https://www.w3schools.com/js/pic_htmltree.gif "DOM Tree")

The W3C DOM standard is separated into 3 different parts:

- Core DOM - standard model for all document types
- XML DOM - standard model for XML documents
- HTML DOM - standard model for HTML documents

### 1. The getElementById method
    
Access an element via id.

### 2. The innerHTML property

Get or replace the inner HTML of an element.
    
#### Example

```js
document.getElementById("demo").innerHTML = "Hello World!"
```

This example changes the `innerHTML` of the element with `id="demo"` to "Hello World!".

## 2 Finding HTML Elements

| Find Elements by| Example| Explain
|---|---|---|
Id| `document.getElementById("app")`| Finds the element with `id="app"`. If found,  return the element as an `object`. Else, return `null`.
Tag Name| `document.getElementById("app").getElementsByTagName("p")`| Finds the element with `id="app"`, then finds all `<p>` elements inside `"app"`.
Class Name |`document.getElementsByClassName("intro")` | Returns a list of all elements with `class="intro"`.
CSS Selectors | `document.querySelectorAll("#app p.intro")`| Returns a list of (all `<p>` elements with `class="intro"` that are children of the id `app`).
HTML Object Collections | `document.getElementsByTagName("p")[1]`| Returns the second `<p>` element.

## 3 DOM Events

A JS can be executed when an event occurs, like when a user clicks on an HTML element.

Below are some examples of HTML events.

| Event Attribute| Meaning
|---|---|
onmousedown| When a mouse-button is clicked
onmouseup| When the mouse-button is released
onclick| When the mouse-click is completed
onmouseover| When the mouse moves over an element
onmouseout| When the mouse moves out of an element
onchange| When an input field is changed 

### 1. The addEventListener() method

The `addEventListener()` method attaches an event handler (which is a `function`) to a specified element without overwriting existing event handlers.

#### Syntax

```js
element.addEventListener(event, function, useCapture)
```

The first parameter is the type of the event (like "`click`" or "`mousedown`")

The second parameter is the function we want to call when the event occurs.

The third parameter is a boolean value specifying whether to use event bubbling or event capturing. This parameter is optional.

#### Example

```js
document.getElementById("myBtn").addEventListener("click", ()=>{alert("Hello World!")})
```

This example alerts "Hello World!" when the element with `id="myBtn"` is clicked.

#### Event Bubbling or Event Capturing?

There are two ways of event propagation in the HTML DOM, bubbling and capturing.

Event propagation is a way of defining the element order when an event occurs. If you have a <p> element inside a <div> element, and the user clicks on the <p> element, which element's "click" event should be handled first?

In bubbling the inner most element's event is handled first and then the outer: the <p> element's click event is handled first, then the <div> element's click event.

In capturing the outer most element's event is handled first and then the inner: the <div> element's click event will be handled first, then the <p> element's click event.

With the addEventListener() method you can specify the propagation type by using the "useCapture" parameter (the third parameter).

The default value is false, which will use the bubbling propagation, when the value is set to true, the event uses the capturing propagation.

## 4 DOM Navigation

### 1. DOM Nodes

According to the W3C HTML DOM standard, everything in an HTML document is a node.

With the HTML DOM, using JS, new nodes can be created, and all nodes can be accessed, modified or deleted.

You can use the following node properties to navigate between nodes with JavaScript:

- `parentNode`
- `childNodes[nodenumber]`
- `firstChild`
- `lastChild`
- `nextSibling`
- `previousSibling`

### 2. HTMLCollection

The `getElementsByTagName()` method returns an `HTMLCollection` object.

An `HTMLCollection` object is a collection of HTML elements.

### 3. NodeList

A NodeList object is a list (collection) of nodes extracted from a document.

A NodeList object is almost the same as an HTMLCollection object.

#### The Difference Between an HTMLCollection and a NodeList

A NodeList and an HTMLcollection is very much the same thing.

Similarity: 

- Both are array-like collections (lists) of nodes (elements) extracted from a document.
- The index starts at 0.
- The nodes can be accessed by index numbers.
- Both have a length property that returns the number of elements in the list (collection).| 

Difference:

| HTMLCollection| NodeList
|---|---|
An HTMLCollection is a collection of document elements.| A NodeList is a collection of document nodes (element nodes, attribute nodes, and text nodes).
HTMLCollection items can be accessed by their name, id, or index number.| NodeList items can only be accessed by their index number.
An HTMLCollection is always a **live** collection. Example: If you add a `<li>` element to a list in the DOM, the list in the HTMLCollection will also change.| A NodeList is most often a **static** collection. Example: If you add a `<li>` element to a list in the DOM, the list in NodeList will not change.

The `getElementsByClassName()` and `getElementsByTagName()` methods return a **live** HTMLCollection.

The `querySelectorAll()` method returns a **static** NodeList.

The childNodes property returns a **live** NodeList.





