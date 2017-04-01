TBA - Use NPM to install the d3 library locally and run a script that uses the d3 library on the server-side.

https://www.npmjs.com/package/d3


Create a new script:

```` js
var d3 = require("d3") // assign the locally-installed D3 module to a variable called d3. this is the server-side equivalent of how we load the d3 library on the client-side using an external script.

var a = [2,3,4,5]

var max = d3.max(a)

console.log("MAX: ", max)
````

Execute the script:

```` js
npm run ________
````
