## Node.js - Running JavaScript on the Server Side

Up until this point we have been learning and practicing JavaScript within the context of client-side development. That is, all our JavaScript has been executed and interpreted by a web browser.

[Node.js](https://nodejs.org/en/) allows us to install an interpreter onto our local machines that will allow us to run JavaScript scripts on the server-side.

> Node.js is a JavaScript runtime built on Chrome's V8 JavaScript engine. Node.js uses an event-driven, non-blocking I/O model that makes it lightweight and efficient. Node.js' package ecosystem, npm, is the largest ecosystem of open source libraries in the world. - [Node.js website](https://nodejs.org/en/)

### Documentation and Reference

Source Code: https://github.com/nodejs/node.

API Documentation: https://nodejs.org/api/.

### Installation

First, check if node is installed on your computer, and if so, which version:

```` sh
# Mac Terminal:
which node
# Windows Command Prompt:
where node
#> /Users/YOUR_USERNAME/.nvm/versions/node/v6.6.0/bin/node

node -v
#> v6.6.0
````

If Node isn't already installed on your computer, you need to install it. There are two general ways to install Node. The first is by simply installing a specific version. The second is by installing a version manager and using that to install a specific version. The latter strategy, while potentially more complex, provides the ability to install new versions and switch between versions with ease. Using version managers is a software development best practice.

> NOTE: Some students have reported issues installing and using the version manager. If the version manager isn't working for you, alternatively install Node.js from https://nodejs.org/en/download/.

#### Node Version Manager (Mac)

Install the [Node Version Manager for Mac](https://github.com/creationix/nvm):

```` sh
curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.32.0/install.sh | bash
````

#### Node Version Manager (Windows)

Install the [Node Version Manager for Windows](https://github.com/coreybutler/nvm-windows) by following its [installation instructions](https://github.com/s2t2/nvm-windows#installation--upgrades).











### Usage

Once you have installed Node, you should be able to use it to run scripts. Create a new `my_script.js` file on your Desktop and populate it with the following contents:

```` js
console.log("HEY WE ARE RUNNING JAVASCRIPT ON THE SERVER-SIDE!")
````

Run the script:

```` sh
node my_script.js
#> HEY WE ARE RUNNING JAVASCRIPT ON THE SERVER-SIDE!
````

> NOTE: You either need to run the script from within the directory where it exists, or invoke it with a more specific file path (e.g. `node ~/Desktop/some-folder/my_script.js`).

Nice Job.
