# JS Web APIs

A Web API is a developer's dream.

- It can extend the functionality of the browser
- It can greatly simplify complex functions
- It can provide easy syntax to complex code

## 1 Application Programming Interface

### 1. What is Web API?

API stands for Application Programming Interface.

A Web API is an application programming interface for the Web.

A Browser API can extend the functionality of a web browser.

A Server API can extend the functionality of a web server.

### 2. Browser APIs

All browsers have a set of built-in Web APIs to support complex operations, and to help accessing data.

### 3. Third Party APIs
Third party APIs are not built into your browser.

To use these APIs, you will have to download the code from the Web.

Examples:

- YouTube API - Allows you to display videos on a web site.
- Twitter API - Allows you to display Tweets on a web site.
- Facebook API - Allows you to display Facebook info on a web site.

## 2 Fetch API

The Fetch API interface allows web browser to make HTTP requests to web servers.

### 1. A Fetch API Example

The example below fetches a file and displays the content:

#### Example

```js
let file = "fetch_info.txt"
fetch(file)
.then(myFile => myFile.text())
.then(myText => document.getElementById("test").innerHTML = myText)
```

