## Node.js - Running JavaScript on the Server Side

### Node Package Manager (NPM)

When running JavaScript on the server, you don't have access to client-side, browser-related objects like the DOM or the browser window. But you do have access to load third-party libraries, some of which we have already become familiar with (e.g. D3).

In the Node ecosystem, third-party libraries are called "packages" and the software used to install and manage these libraries is called the [Node Package Manager (NPM)](https://www.npmjs.com/).

NPM usually comes pre-installed when you install Node. Check to see if NPM is installed, and if so, which version:

```` sh
# Mac Terminal:
which npm
# Windows Command Prompt:
where npm
#> /Users/YOUR_USERNAME/.nvm/versions/node/v6.6.0/bin/npm

npm -v
#> 3.10.3
````

#### Installing Packages

When installing third-party packages, you have the option to install them "globally" or "locally," and the installation method differs slightly for each.

```` sh
npm install MODULE_NAME
````

##### Global Installations

When you install a package "globally" you install it onto your machine for use within any of your projects. Often, we install packages globally when we need to access their command-line utilities.

```` sh
npm install MODULE_NAME -g
````

One example of a package we will install globally is the `express-generator` package, which we will later use to generate the directory structure of a starter web application.

##### Local Installations

When  you install a package "locally" you install it within the directory of a specific project you are working on. In this case, only files within the project will have access to the installed module. This is often useful if you are working on multiple projects at the same time which use different modules or different versions of the same module. Local module installations are a way to keep your project dependancies separate from each other.

To manage the module dependancies of your project, create a new file called `package.json` in that project's root directory (most commonly by running the `npm init` command in that directory). Then within the `package.json` file, specify a list of packages and their versions. From within the project's root directory, run `npm install` to install all packages listed in the `package.json` file.

```` sh
npm install # if using a package.json file to list package dependancies

# ... or ...

npm install MODULE_NAME --save # will install the module locally and automatically add it to the list of dependancies in the package.json file
````

Additional documentation on `package.json`:

  + https://docs.npmjs.com/files/package.json
  + https://docs.npmjs.com/files/package.json#main
  + https://docs.npmjs.com/files/package.json#scripts
