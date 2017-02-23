# JavaScript Language Overview

## Syntax and Style

You may see JavaScript statements ended with a trailing semi-colon. In some cases it is necessary to use these trailing semi-colons, but you are generally free to omit them.

Always observe lower-case variable and function names. If your variable or function name is comprised of two words, use camel-case, not snake case or title-case.

```` js
// DO:
name
firstName
lastName
firstAndLastName

// DON'T:
Name
first_name
LastName
first_and_last_name
````

### Comments

Reference https://www.w3schools.com/js/js_comments.asp.

Single-line comments:

```` js
console.log("HELLO WORLD") // single-line comment
// console.log("HELLO WORLD - THIS MESSAGE IS PREVENTED FROM BEING EXECUTED")
````

Multi-line comments:

```` js
/*

multi-line comment

console.log("HELLO WORLD - THIS MESSAGE IS PREVENTED FROM BEING EXECUTED")

*/
````















## Logging and Debugging

### Logging

Output, or "log" an object to the browser's console:

```` js
console.log("HELLO WORLD")
````

Log multiple objects:

```` js
console.log("HELLO WORLD", 5, 9999, "GOODBYE!")
````

### Debugging

Dropping the following line
```` js
debugger;
````

For example:

```` js
function debugStuff(){
  console.log("START OF FUNCTION");
  var x = 100;
  debugger;
  var y = 999;
  console.log("END OF FUNCTION");
}

debugStuff()
x //=> 100
y //=> undefined
````























## Functions

Like in other languages, JavaScript functions must first be defined before they can be invoked (or called).

Define a function:

```` js
function doStuff(){
  console.log("DOING STUFF HERE!")
}
````

Invoke the function:

```` js
doStuff() // NOTE: the trailing parentheses are important. If they are omitted, the function will not be invoked.
````

You might see some functions invoked by themselves (e.g. `doStuff()`) while others are invoked on objects (e.g. `someObject.doSomethingElse()`).

Many of the examples below involve invoking built-in functions on certain types of objects. To find a comprehensive list of functions available to be called on any given type of object, reference the documentation for that type of object.

### Parameters

Some functions accept parameters which can be passed to the function during its invocation. A function's parameters must be configured during the function's definition.

#### Single Parameter

Define a function with a parameter:

```` js
function doStuffWithParam(message){
  console.log(message)
}
````

In this case, `message` is the name of the function's parameter. Invoke it like so:

```` js
doStuffWithParam("My Message Here")
````

#### Multiple Parameters

Define a function with multiple parameters:

```` js
function doStuffWithParams(message, firstName, lastName){
  console.log("DOING STUFF HERE!")
  console.log(message, "says", firstName, lastName)
}
````

In this case, `message`, `firstName` and `lastName` are the names of the function's parameters. Invoke it like so:

```` js
doStuffWithParams("HO HO HO", "Santa", "Claus")
````

### Returns

Use the `return` keyword when you want to make use of the value returned by the function:

```` js
function calculateArea(length, height){
  length * height
}

var area = calculateArea(4, 2)
area //=> undefined
````

```` js
function calculateArea(length, height){
  return length * height
}

var area = calculateArea(4, 2)
area //=> 8
````














## Variables

Declare a variable using the syntax `var` then the name of the variable, then assign its value by using a single equal sign (`=` )followed by the value. Any datatype can be stored in a variable.

```` js
var i = 10
var f = 0.45
var s = "My Message"
var d = new Date(2017,02,23)
var a = [1,2,3,4]
var o = {}
````

> NOTE: when assigning a value, use a single equal sign (`=`).

Variables can be defined without yet being assigned a value. In this case, the variable's value is said to be "undefined".

```` js
var g; //=> "undefined"
g = 100
g //=> 100
````

## Datatypes

Use `typeof()` to return the type of any object:

```` js
typeof("Hello") //=> "string"
typeof(100) //=> "number"
typeof(0.45) //=> "number"
typeof(true) //=> "boolean"
typeof(false) //=> "boolean"
typeof(undefined) //=> "undefined"
typeof( {a:1, b:2} ) //=> "object"
typeof( [1,2,3] ) //=> "object" (array)
typeof( new Date() ) //=> "object" (date)
typeof( function doStuff(){} ) //=> "function"
````

Here are a few examples of how to convert between datatypes:

```` js
parseInt("500") // converts string to number
parseFloat("0.45") // converts string to number
Date.parse("March 21, 2012") // converts string to unix timestamp
````

```` js
var i = 100
i.toString() //=> "100"
````

See the subsections below for more information about the different data types.

### Booleans

Reference: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean.

In JavaScript, like other languages, `true` and `false` are reserved words which indicate boolean values.

```` js
true
false
````

The most relevant boolean operator is the equality operator:

```` js
true == true //=> true
true == false //=> true
false == false //=> false
````

### Strings

Reference: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String.

```` js
"Hello World"
````

Example string functions:

```` js
"Hello".toUpperCase() //=> "HELLO"
"Hello" + "World" //=> "Hello World" (string concatenation)
"Hello World".split(" ") //=> ["Hello", "World"]
"Hello World".includes("Hel") //=> true
"Hello World".includes("Gur") //=> false
````

Strings also support equality operators:

```` js
"Hello" == "Hello" //=> true
"Hello" == "Hel" //=> false
````

### Numbers

Reference: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number.

```` js
100
-100
0.45
````

Numeric functions include many arithmetic operators:

```` js
100 + 5
100 - 5
100 * 5
100 / 5
````

Indicate order of operations by using parentheses:

```` js
3 + 1 * 2 //=> 5
(3 + 1) * 2 //=> 8
````

Numbers also support equality operators:

```` js
100 == 100 //=> true
100 == 100.0 //=> true
100 == 99 //> false
100 == (99 + 1) //=> true
````

### Arrays

Reference: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array

Arrays are ordered lists. Arrays contain zero or more elements. Arrays can contain elements of any type. As a best practice, array elements should share a datatype and structure:

```` js
// DO:

[]
[1,2,3,4]
[100, 75, 33]
["fun", "times", "right?"]
[ {a:1, b:2}, {a:5, b:6}]
[ [1,2,3], [4,5,6], [7,8,9]] // arrays "nested" inside another array

// DON'T:
[100, "fun"]
[ {a:1, b:2}, {c:5, d:6}]
````

Like other languages, individual array elements can be accessed by their index. Array indices are zero-based, meaning the index of the first element in an array is 0.

```` js
var arr = ["a", "b", "c", "d"]
arr[0] //=> "a"
arr[1] //=> "b"
arr[2] //=> "c"
arr[3] //=> "d"
arr[4] //=> undefined

arr.indexOf("a") //> 0
arr.indexOf("b") //> 1
arr.indexOf("c") //> 2
arr.indexOf("z") //> -1 (applies to any item not found in the array)
````

Common array functions and operators include:

```` js
var arr = ["a", "b", "c", "d"]
a.length //=> 4
arr.includes("a") //=> true
arr.includes("z") //=> false
````

Add an element to the end of an array:

```` js
var arr = ["a", "b", "c", "d"]
arr.push("e") //> "e"
arr //> ["a", "b", "c", "d", "e"] (MUTATING)
````

Concatenate two arrays:

```` js
var arr = ["a", "b", "c", "d"]
var arr2 = ["x", "y", "z"]
var arr3 = arr.concat(arr2)
arr //=> ["a", "b", "c", "d"] (NON-MUTATING)
arr2 //=> ["x", "y", "z"] (NON-MUTATING)
arr3 //=> "a", "b", "c", "d", "x", "y", "z"]
````

#### Iteration

Arrays can be iterated, or "looped" using the `forEach()` function:

```` js
var arr = ["a", "b", "c", "d"]

arr.forEach(function(item, index, array) { // uses all available params
  console.log(item, index);
})

arr.forEach(function(item) { // uses the most simple params possible
  console.log(item);
})
````

Arrays can be looped "in-place" using the `map()` function:

```` js
var arr = [1, 2, 3, 4]

var arr2 = arr.map(function(x){
  return x * 100
})

arr2 //=> [100, 200, 300, 400]
````

> NOTE: remember to use the `return` keyword when mapping.

### Objects

Reference: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object.

JavaScript objects comprise curly braces (`{}`) containing one or more key/value pairs, with the key separated from the value by a colon (`:`) and each key/value pair separated by a comma (`,`). In this respect they resemble Python's "dictionary" datatype or Ruby's "hash" datatype.

**JavaScript Object Notation** is referred to as `JSON`. Files ending in .json contain a javascript object.

```` js
{}
{a:1, b:2, c:3}
{a:1, b:2, c:3, fruits:["apple","banana","pear"]} // objects can contain arrays
{first:"Santa", last:"Claus", message:"Ho Ho Ho"}
````

Access individual object elements by their key:

```` js
var person = {first:"Santa", last:"Claus", message:"Ho Ho Ho", stops:["New York", "Denver", "San Francisco"]}
person["first"] //> "Santa"
person["last"] //> "Claus"
person["message"] //> "Ho Ho Ho"
person["stops"] //=> ["New York", "Denver", "San Francisco"]
person["stops"][1] //=> "Denver" (an array is still an array, even if it exists inside a JSON object)
````

Add or remove items from an object:

```` js
var person = {first:"Santa", last:"Claus", message:"Ho Ho Ho", stops:["New York", "Denver", "San Francisco"]}
person["wife"] = "Mrs. Claus"
delete person["stops"];
person //=> {first: "Santa", last: "Claus", message: "Ho Ho Ho", wife: "Mrs. Claus"}
````
