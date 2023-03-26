# JS JSON

## 1 JavaScript Object Notation

### 1. What is JSON?

- JSON stands for JavaScript Object Notation
- JSON is a text format for storing and transporting data
- JSON is plain text written in JS object notation
- JSON is used to send data between computers
- JSON is language independent

### 2. Why Use JSON?

The JSON format is syntactically similar to the code for creating JS objects. Because of this, a JS program can easily convert JSON data into JS objects.

Since the format is text only, JSON data can easily be sent between computers, and used by any programming language.

JS has a function for converting JSON strings into JS objects: `JSON.parse()`

JS's function for converting an object into a JSON string: `JSON.stringify()`

When storing data, the data has to be a certain format, and regardless of where you choose to store it, text is always one of the legal formats.

JSON makes it possible to store JS objects as text.

## 2 Syntax

### 1. Rules

JSON syntax is derived from JS object notation syntax:

- Data is in name/value pairs
- Data is separated by commas
- Curly braces hold objects
- Square brackets hold arrays

### 2. Values

In JSON, values must be one of the following data types:

- a string
- a number
- an object (JSON object)
- an array
- a boolean
- null

JSON values can't be:

- a function
- a date
- undefined

In JSON, string values must be written with double quotes.

## 3 JSON vs XML

Both JSON and XML can be used to receive data from a web server.

| JSON is Like XML because| JSON is better than XML because
|---|---|
Both are "self describing" (human readable)| JSON doesn't use end tag
Both are hierarchical (values within values)| JSON is shorter
Both can be parsed and used by lots of programming languages| JSON is quicker to read and write
Both can be fetched with an XMLHttpRequest| JSON can use arrays

The biggest difference is: XML has to be parsed with an XML parser. JSON can be parsed by a standard JS function.

For AJAX applications, JSON is faster and easier than XML:

Using XML:

- Fetch an XML document
- Use the XML DOM to loop through the document
- Extract values and store in variables

Using JSON:

- Fetch a JSON string
- JSON.Parse the JSON string

#### Example

JSON: 

```json
{"employees":[
  { "firstName":"John", "lastName":"Doe" },
  { "firstName":"Anna", "lastName":"Smith" }
]}
```

XML: 

```xml
<employees>
  <employee>
    <firstName>John</firstName> <lastName>Doe</lastName>
  </employee>
  <employee>
    <firstName>Anna</firstName> <lastName>Smith</lastName>
  </employee>
</employees>
```

## 4 JSON Functions

### 1. JSON.parse()

When receiving data from a web server, the data is always a string.

Parse the data with `JSON.parse()`, and the data becomes a JS object.

#### Example

```js
JSON.parse('{"name":"John", "age":30, "city":"New York"}')
```

### 2. JSON.stringify()

When sending data to a web server, the data has to be a string.

Convert a JS object into a string with `JSON.stringify()`.

#### Example:

```js
JSON.stringify({name: "John", age: 30, city: "New York"})
```

## 5 JSON Literals

### 1. Object Literals:

This is a JSON string:

```js
'{"name":"John", "age":30, "car":null}'
```

Inside the JSON string there is a JSON object literal:

```json
{"name":"John", "age":30, "car":null}
```

It is a common mistake to call a JSON object literal "a JSON object".

JSON cannot be an object. JSON is a string format.

The data is only JSON when it is in a string format. When it is converted to a JS variable, it becomes a JS object.

### 2. Array Literals:

This is a JSON string:

```js
'["Ford", "BMW", "Fiat"]'
```

Inside the JSON string there is a JSON array literal:

```json
["Ford", "BMW", "Fiat"]
```




