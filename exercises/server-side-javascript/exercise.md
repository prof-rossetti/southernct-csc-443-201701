# Server-side JavaScript Exercise

Use NPM to create a new Node.js project, install a third-party open source JavaScript library, and execute a script which utilizes that library.

## Objectives

  1. Gain exposure to initializing a new NPM project.
  2. Gain familiarity with the contents of a NPM project's `package.json` file.
  3. Gain exposure to installing third-party open source NPM modules.
  4. Gain exposure to running Node.js scripts.

## Prerequisites

  + [Node.js Overview](/notes/javascript/node.md)
  + [Node Package Management Overview](/notes/javascript/npm.md)

## Instructions

### Create a New Project

Initialize a new Node.js project:

```` sh
cd ~/Desktop
mkdir my_program
cd my_program
npm init # then answer some questions and/or press enter a few times...
````

This initialization will create a new file called `package.json` in your project directory. This is essentially what defines an NPM project.

The `package.json` file contains not only metadata about the project, like its name, description, and author. But it also defines functional components of the project, like the names and versions of all the project's dependancies, and the commands used to test and run the software.

### Install Package Dependancies

So far we have not specified any package dependancies (i.e. any other libraries ours might need in order to function). But we still need to run an important command to finish setting-up our NPM project directory:

```` sh
npm install
````

This command, when run for the first time, creates a new directory in your project called `node_modules`. This directory will house any dependent modules we might need. This is analogous to storing external JS and CSS scripts in the directory of a website project.

> Pro Tip: a common best-practice is to prevent all contents of the `node_modules` directory from being tracked in version control. Do so by configuring a file called `.gitignore` in your project's root directory, and adding into it a line that specifies the name of that directory, which in this case is: `node_modules/`.

### Create a new Script

During the project initialization, you were asked to specify an "entry point" or leave the default entry point as `index.js`. This "entry point" of an NPM project is somewhat analogous to the entry point of a website project being its `index.html` file in the sense that the server looks for that file to define the website's home page.

Create an `index.js` file and paste in it the following contents:

```` js
console.log("RUNNING RUNNING RUNNING")
````

### Run the script

#### Executing via Node.js

There are two ways to execute the script. The first is a generic Node.js way, where you invoke `node` to run the script:

```` js
node index.js
````

#### Executing via NPM

The other way is a more NPM-specific approach whereby you register that particular Node command by adding a new named entry to the `scripts` part of the `package.json` file.

First, edit your `package.json` file by registering a new "script". Your updated file might look something like the following, where the new script added is called `go-go-go` and the command registered to that script is `node index.js`:

```` js
{
  "name": "my_program",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1", // don't forget this comma
    "go-go-go": "node index.js" // this is the new line we added
  },
  "author": "",
  "license": "ISC"
}
````

Next, run the script:

```` js
npm run go-go-go
````

Nice. We are half-way done.

### Install an Open Source NPM Package

We're familiar with using the D3 JavaScript library on the client-side for various purposes. When we were using it from the client-side, we either downloaded the files locally or we referenced them as an external script. Because the D3 library is also available as an NPM package, we can use NPM to install and use it in our project.

Install the [D3 NPM package](https://www.npmjs.com/package/d3) locally, that is - into the project's `node_modules` directory:

```` sh
npm install d3 --save
````

Take a look at the project's `package.json` file, and observe it now contains a corresponding entry in the "dependencies" section.

Take a look at the project's `node_modules` directory, and observe it now contains a number of D3-related libraries.

If you are tracking your project in version control and haven't yet added the `node_modules` directory into your `.gitignore` file, now is a great time to do so, to prevent those D3 libraries from being committed and bloating the size of your project's Git repository.

### Use the Package in your Script

Edit the contents of your `index.js` file to use some trivial D3 method like `d3.max()`:

```` js
console.log("RUNNING RUNNING RUNNING")

var d3 = require("d3") // assign the locally-installed D3 module to a variable called d3 for further invocation. You can choose any variable name you want, but why not choose the official name we're already familiar with?

var someIntegers = [9, 13, 99, 3]
console.log("THE ARRAY IS:", someIntegers)

var maxNumber = d3.max(someIntegers)
console.log("MAXIMUM NUMBER IN THE ARRAY IS:", maxNumber)
````

Execute the script again to see if it worked:

```` js
npm run go-go-go
````

Congratulations, you are server-side programming!
