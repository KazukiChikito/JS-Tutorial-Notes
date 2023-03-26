# JS AJAX

AJAX is a developer's dream, because you can:

- Read data from a web server - after the page has loaded
- Update a web page without reloading the page
- Send data to a web server - in the background

## 1 Overview

### What is AJAX?

AJAX = Asynchronous JavaScript And XML.

AJAX is not a programming language.

AJAX just uses a combination of:

- A browser built-in XMLHttpRequest object, to request data from a web server
- JS and HTML DOM, to display or use the data

> AJAX is a misleading name. AJAX applications might use XML to transport data, but it is equally common to transport data as plain text or JSON text.

AJAX allows web pages to be updated asynchronously by exchanging data with a web server behind the scenes. This means that it is possible to update parts of a web page, without reloading the whole page.

### How AJAX Works

![How AJAX Works](https://www.w3schools.com/js/pic_ajax.gif)

1. An event occurs in a web page (the page is loaded, a button is clicked)
2. An XMLHttpRequest object is created
3. The object sends a request to a web server
4. The server processes the request
5. The server sends a response back to the web page
6. The response is read
7. Proper action (like page update) is performed

### Fetch API
>Modern Browsers can use Fetch API instead of the XMLHttpRequest Object.
>The Fetch API interface allows browsers to make HTTP requests to servers.
>If you use the XMLHttpRequest Object, Fetch can do the same in a simpler way.

## 2 The XMLHttpRequest Object

The XMLHttpRequest object can be used to exchange data with a web server behind the scenes. This means that it is possible to update parts of a web page, without reloading the whole page.

1. Create an XMLHttpRequest Object
2. Define a Callback Function
3. Open and Send a Request to a server

#### Example

```js
const xhttp = new XMLHttpRequest()

xhttp.onload = function() {
  // Here you can use the Data
  document.getElementById("demo").innerHTML = this.responseText
}

xhttp.open("GET", "ajax_info.txt")
xhttp.send()
```

### Access Across Domains
For security reasons, modern browsers do not allow access across domains.

This means that both the web page and the XML file it tries to load, must be located on the same server.

## 3 Request

### Example

```js
xhttp.open("GET", "ajax_info.txt", true)
xhttp.send()
```

### Syntax

| Method|	Description
|---|---|
open(method, url, async)|	Specifies the type of request
send()|	Sends the request to the server (used for GET)
send(string)|	Sends the request to the server (used for POST)

*method*: the type of request: GET or POST
*url*: the server (file) location
*async*: true (asynchronous) or false (synchronous)

### 1. Method: GET or POST?

`GET` is simpler and faster than `POST`, and can be used in most cases.

However, always use POST requests when:

- A cached file is not an option (update a file or database on the server).
- Sending a large amount of data to the server (POST has no size limitations).
- Sending user input (which can contain unknown characters), POST is more robust and secure than GET.

#### GET Requests

A simple GET request:

```js
xhttp.open("GET", "demo_get.asp")
xhttp.send()
```

If you want to send information with the GET method, add the information to the URL:

```js
xhttp.open("GET", "demo_get2.asp?fname=John&lname=Doe")
xhttp.send()
```

#### POST Requests

A simple POST request:

```js
xhttp.open("POST", "demo_post.asp")
xhttp.send()
```

To POST data like an HTML form, add an HTTP header with `setRequestHeader()`. Specify the data you want to send in the `send()` method:

```js
xhttp.open("POST", "ajax_test.asp")
xhttp.setRequestHeader("Content-type", "application/x-www-form-urlencoded")
xhttp.send("fname=John&lname=Doe")
```


|Method|	Description
|---|---|
setRequestHeader(header, value)|	Adds HTTP headers to the request
*header*: specifies the header name
*value*: specifies the header value

### 2. The url - A File On a Server

The url parameter of the open() method, is an address to a file on a server:

```js
xhttp.open("GET", "ajax_test.asp", true)
```

The file can be any kind of file, like .txt and .xml, or server scripting files like .asp and .php (which can perform actions on the server before sending the response back).

### 3. Asynchronous - True or False?

Server requests should be sent asynchronously.

The async parameter of the `open()` method should be set to true:

```js
xhttp.open("GET", "ajax_test.asp", true)
```

By sending asynchronously, the JS does not have to wait for the server response, but can instead:

- execute other scripts while waiting for server response
- deal with the response after the response is ready

>The default value for the async parameter is `async = true`. You can safely remove the third parameter from your code.
>Synchronous XMLHttpRequest (`async = false`) is not recommended because the JS will stop executing until the server response is ready. If the server is busy or slow, the application will hang or stop.

## 4 Response

### 1. Server Response Properties

| Property|	Description
|---|---|
responseText|	get the response data as a string
responseXML|	get the response data as XML data

#### The responseText Property

The `responseText` property returns the server response as a string, and you can use it accordingly:

```js
document.getElementById("app").innerHTML = xhttp.responseText
```

#### The responseXML Property

The XMLHttpRequest object has an in-built XML parser.

The `responseXML` property returns the server response as an XML DOM object.

Using this property you can parse the response as an XML DOM object.

```js
  document.getElementById("app").innerHTML = this.responseXML
```

### 2. Server Response Methods

| Method|	Description
|---|---|
getResponseHeader()|	Returns specific header information from the server resource
getAllResponseHeaders()|	Returns all the header information from the server resource

#### The getAllResponseHeaders() Method

The `getAllResponseHeaders()` method returns all header information from the server response.

#### The getResponseHeader() Method
The `getResponseHeader()` method returns specific header information from the server response:

```js
const xhttp = new XMLHttpRequest()
xhttp.onload = function() {
    document.getElementById("demo").innerHTML = this.getResponseHeader("Last-Modified")
}
xhttp.open("GET", "ajax_info.txt")
xhttp.send()
```
