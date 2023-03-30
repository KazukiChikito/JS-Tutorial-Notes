# JS vs jQuery

jQuery was created in 2006 by John Resig. It was designed to handle Browser Incompatibilities and to simplify HTML DOM Manipulation, Event Handling, Animations, and Ajax.

However, after JavaScript Version 5 (2009), most of the jQuery utilities can be solved with a few lines of standard JS.

Below are some examples about the difference syntax between JS and jQuery.

## 1 Selectors

Finding HTML Elements by:

| Objective| JS| jQuery
|---|---|---|
Id| `document.getElementById("app")`| `$("#app")`
Tag Name| `document.getElementsByTagName("p")`| `$("p")`
Class Name| `document.getElementsByClassName("demo")`| `$(".demo")`
CSS Selectors| `document.querySelectorAll("p.demo")`| `$("p.demo")`

## 2 HTML

| Objective| JS| jQuery
|---|---|---|
Set HTML Content| `myElement.innerHTML = "<p>Hello World</p>"`| `myElement.html("<p>Hello World</p>"`)
Get HTML Content| `myElement.innerHTML`| `myElement.html()`

## 3 CSS

Actions done to HTML Elenents:

| Objective| JS| jQuery
|---|---|---|
Hiding | `myElement.style.display = "none"`| `myElement.hide()`
Showing | `myElement.style.display = ""`| `myElement.show()`
Styling | `document.getElementById("demo").style.fontSize = "16px"`| `$("#demo").css("font-size","35px")`

## 4 DOM

| Objective| JS| jQuery
|---|---|---|
Removing HTML Elements| `document.getElementById("app").remove()`| `$("#app").remove()`
Get Parent Element| `document.getElementById("content").parentNode.nodeName`| `$("#content").parent().prop("nodeName")`
