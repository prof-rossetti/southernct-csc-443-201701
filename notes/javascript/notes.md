# JavaScript Language Overview

This document contains a highlight of common JavaScript language considerations. For an in-depth documentation, reference: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference and https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements.

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
console.log("HELLO WORLD") //> HELLO WORLD
````

Log multiple objects:

```` js
console.log("HELLO WORLD", 5, 9999, "GOODBYE!")  //> HELLO WORLD 5 9999 GOODBYE!
````

### Debugging

Insert a `debugger` statement to drop a break-point in script execution. When the break-point is reached, it will stop and allow you to interact with the state of the code at that particular line.

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


> Feel free to come back to this `debugger`  example after you have familiarized yourself with functions, below.




















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

Declare a variable using the syntax `var` then the name of the variable, then assign its value by using a single equal sign (`=`) followed by the value. Any datatype can be stored in a variable.

```` js
var i = 10
var f = 0.45
var s = "My Message"
var d = new Date(2017,02,23)
var a = [1,2,3,4]
var o = {}
var f = function(){ console.log("LOGGING FROM INSIDE A FUNCTION") }

// REFRESHER ON FUNCTION INVOCATION:
f //=> function (){ console.log("LOGGING FROM INSIDE A FUNCTION") }
f() //> LOGGING FROM INSIDE A FUNCTION
````

> NOTE: when assigning a value, use a single equal sign (`=`).

Variables can be defined without yet being assigned a value. In this case, the variable's value is said to be "undefined".

```` js
var g; //=> undefined
g = 100
g //=> 100
````

## Datatypes

Use `typeof()` to return the type of any object:

```` js
typeof("Hello") //=> string
typeof(100) //=> number
typeof(0.45) //=> number
typeof(true) //=> boolean
typeof(false) //=> boolean
typeof(undefined) //=> undefined
typeof( {a:1, b:2} ) //=> object
typeof( [1,2,3] ) //=> object
typeof( new Date() ) //=> object
typeof( function doStuff(){} ) //=> function
````

Here are a few examples of how to convert between datatypes:

```` js
// convert string to number:
parseInt("500")

// convert string to number:
parseFloat("0.45")

// convert string to unix timestamp:
Date.parse("March 21, 2012")

// convert number to string:
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

> "Is this equal to that?"

Also relevant is the inequality operator:

```` js
true != true //=> false
true != false //=> true
false != false //=> false
````

> "Is this not equal to that?"

Reference https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_Operators#Comparison_operators for more information about comparison operators.

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

Reference: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_Operators#Arithmetic_operators for more information about arithmetic operators.

#### `Math` Methods

Also reference the functionality of the "Math" object: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math.

```` js
Math.PI //=> 3.141592653589793

Math.random()

Math.round(4.555) //=> 5
Math.ceil(4.555) //=> 5
Math.floor(4.555) //=> 4

Math.min(4,3,7,9) //=> 3
Math.max(4,3,7,9) //=> 9
````

### Arrays

Reference: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array.

Arrays are ordered lists. Arrays contain zero or more elements. Arrays can contain elements of any type. As a best practice, array elements should share a datatype and structure:

```` js
// DO:

[]
[1,2,3,4]
[100, 75, 33]
["fun", "times", "right?"]
[ {a:1, b:2}, {a:5, b:6}] // arrays can contain objects
[ [1,2,3], [4,5,6], [7,8,9]] // arrays can be "nested" inside other arrays

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

A common pattern is to loop through one array to populate the contents of another:

```` js
var arr = [1, 2, 3, 4]
var arr2 = []

arr.forEach(function(item) {
  arr2.push(item * 100)
})

arr //=> [1, 2, 3, 4]
arr2  //=> [100, 200, 300, 400]
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

#### Subsets

##### Filtering

Reference: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter.

Use the `filter()` function to select a subset of items from an array - only those items matching a given condition.

```` js
var arr = [1,2,4,8,16]
arr.filter(function(i){ return true })
arr.filter(function(i){ return i == 2})
arr.filter(function(i){ return i != 2})
arr.filter(function(i){ return i > 2})
arr.filter(function(i){ return i <= 2})
arr.filter(function(i){ return i > 102})
````

```` js
var teams = [{city:"New York", name:"Yankees"}, {city:"New York", name:"Mets"}, {city:"Boston", name:"Red Sox"}]
teams.filter(function(obj){ return obj["name"] == "Yankees" })
teams.filter(function(obj){ return obj["city"] == "New York" })
teams.filter(function(obj){ return obj["city"] == "New Haven" })
teams.filter(function(obj){ return obj["city"].includes("New") })
````

> Note: the `filter()` function returns an Array, even if it is empty or only contains one item.

##### Finding

Reference: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/find.

Use the `find()` function to select a single items from an array - only the first item matching a given condition.

```` js
var arr = [1,2,4,8,16]
arr.find(function(i){ return true })
arr.find(function(i){ return i == 2})
arr.find(function(i){ return i != 2})
arr.find(function(i){ return i > 2})
arr.find(function(i){ return i <= 2})
arr.find(function(i){ return i > 102})
````

```` js
var teams = [{city:"New York", name:"Yankees"}, {city:"New York", name:"Mets"}, {city:"Boston", name:"Red Sox"}]
teams.find(function(obj){ return obj["name"] == "Yankees" })
teams.find(function(obj){ return obj["city"] == "New York" })
teams.find(function(obj){ return obj["city"] == "New Haven" })
teams.find(function(obj){ return obj["city"].includes("New") })

````

> Note: the `find()` function returns a single value, or undefined.

### Objects

Reference: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object.

JavaScript objects comprise curly braces (`{}`) containing one or more key/value pairs, with the key separated from the value by a colon (`:`) and each key/value pair separated by a comma (`,`). In this respect they resemble Python's "dictionary" datatype or Ruby's "hash" datatype.

**JavaScript Object Notation** is referred to as `JSON`. Files ending in .json contain a javascript object. See this repository's [course.json](/course.json) file for an example.

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
person["stops"][1] //=> "Denver" (an array is still an array, even if it exists inside a JSON object!)
````

Add or remove items from an object:

```` js
var person = {first:"Santa", last:"Claus", message:"Ho Ho Ho", stops:["New York", "Denver", "San Francisco"]}
person["wife"] = "Mrs. Claus"
delete person["stops"];
person //=> {first: "Santa", last: "Claus", message: "Ho Ho Ho", wife: "Mrs. Claus"}
````

#### `Object` Methods

Make use of built-in `Object` methods for easier data-processing:

```` js
var person = {first:"Santa", last:"Claus", message:"Ho Ho Ho", stops:["New York", "Denver", "San Francisco"]}
var keys = Object.keys(person) //> ["first", "last", "message", "stops"]
var vals = Object.values(person) //> ["Santa", "Claus", "Ho Ho Ho", Array[3]]
vals[3] //> ["New York", "Denver", "San Francisco"]
var entries = Object.entries(person) //> [Array[2], Array[2], Array[2], Array[2]]
entries[0] //> ["first", "Santa"]
entries[1] //> ["last", "Claus"]
````























## Control Flow

Reference https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference#Control_flow.

### If

In JavaScript, IF statements are defined using the `if` keyword followed by a set of parentheses (`()`) containing an expression to be evaluated, followed by curly braces (`{}`) which contain statements to be executed if that condition is met.

```` js
if (true) {
  console.log("SWEET")
}

if (!true) {
  console.log("SWEET")
}
````

```` js
if (1 == 1) {
  console.log("SWEET")
}

if (1 == 2) {
  console.log("SWEET")
}
````

```` js
if (undefined) {
  console.log("SWEET")
}

if (!undefined) {
  console.log("SWEET")
}

````

IF statements may be followed by the `else` keyword followed by a set of parentheses (`()`) containing an expression to be evaluated in the event none of the above conditions are met.

```` js
if (1 == 1) {
  console.log("SWEET")
} else {
  console.log("NOPE")
}

if (1 == 2) {
  console.log("SWEET")
} else {
  console.log("NOPE")
}
````

IF statements, regardless of whether or not they contain an ELSE statement, can contain any number of `else if` keywords followed by a set of parentheses (`()`) containing an expression to be evaluated in the event that condition is met.

```` js
var fruit = "Apple"

if (fruit == "Orange") {
  console.log("SWEET")
} else if (fruit == "Banana") {
  console.log("OK")
} else {
  console.log("NOPE")
}
````

As in other languages, statement order matters:

```` js
if (false) {
  console.log("SWEET")
} else if (true) {
  console.log("OK")
} else if (true) {
  console.log("ALSO OK")
} else {
  console.log("NOPE")
}
````

### Switch

Switch statements are essentially case statements.

```` js
var fruit = "Apple"

switch(fruit) {
    case "Orange":
        console.log("SWEET")
        break;
    case "Banana":
        console.log("OK")
        break;
    default:
        console.log("NOPE")
}
````

### Errors

#### Throwing Errors

Raise, or "throw" errors yourself:

```` js
throw "MyError"
throw 4
throw true
````

Reference: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/throw.

#### Handling Errors

Handle, or "catch" errors:

```` js
try {
   console.log("TRYING TO DO STUFF HERE")
} catch (err) {
   console.log(err)
}

try {
   throw("OOPS")
   console.log("TRYING TO DO STUFF HERE")
} catch (err) {
   console.log(err)
}
````

Reference: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/try...catch.
