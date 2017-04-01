TBA - Generate a new express application, configure it, and use a local web server to preview it in a browser.

Adapted from [source](http://data-creative.info/process-documentation/2016/04/09/node-for-rails-developers-part-2-node-and-express/).

## Install Express

Use NPM to install a module called the [*Express Generator*](http://expressjs.com/en/starter/generator.html). This package includes the Express package, as well as a command-line utility called the Express Generator for generating new Express applications.

Install Express Generator globally:

```` sh
npm install express-generator -g
````

> NOTE: Passing the `-g` flag denotes a global installation. Global installations generally allow the module to be invoked from the command line.

## Generate an Express Application

Use the Express Generator to generate a skeleton directory structure for a new Express app called "my_app":

```` sh
express my_app --ejs
````

> NOTE: The `--ejs` flag specifies our choice to use *EJS* as a view template engine instead of the default template engine, *Jade*.

This command should create the following files:

    my_app
    my_app/package.json
    my_app/app.js
    my_app/public/images
    my_app/public
    my_app/routes
    my_app/routes/index.js
    my_app/routes/users.js
    my_app/public/stylesheets
    my_app/public/stylesheets/style.css
    my_app/views
    my_app/views/index.ejs
    my_app/views/error.ejs
    my_app/bin
    my_app/bin/www
    my_app/public/javascripts

Don't worry if you're unfamiliar with the location and purpose of each of these files.

### Install Package Dependencies

The role of the `package.json` file is to declare package dependencies. Like the `Gemfile` in Ruby or the `requirements.txt` file in Python.

```` sh
cd my_app
npm install
````

This command installs all NPM module dependencies specified in `package.json`. It creates a new directory called `node_modules/`, where it places the source code for all of these modules. Before committing our project to version control, we'll want to ignore the files in this directory.

Add a `.gitignore` file to the root of your project's directory, for example using the command line:

```` sh
touch .gitignore
````

Then update the contents of the `.gitignore` file to include the following:

```` sh
node_modules/
````

## Running a Local Web Server

Run the development web server.

```` sh
DEBUG=my_app:* npm start
````

You should now be able to visit the application's home page in your browser at `localhost:3000`.

After demonstrating the ability to view the application locally in a browser, stop the web server by typing `ctrl-c`.

## Upgrading Local Web Server

One shortcoming of the default web server is that it requires us to restart the server each time we make a change to one of our application's files. During development, this happens a lot, so we'll want to upgrade our development web server. We can use a module called [Nodemon](______), which will automatically detect file changes and obviate our need to take manual action.

Install Nodemon globally:

```` sh
npm install nodemon -g
````

Modify the web server start script in `package.json` to invoke `nodemon` instead of `node`:

```` js
// package.json
...
  "scripts": {
    "start": "nodemon ./bin/www", // was: "start": "node ./bin/www",
  },
...
````

Restart the web server:

```` sh
DEBUG=my_app:* npm start
````

Congratulations. You've just created a new web application and viewed it locally in a browser. Commit your changes to version control. The next step will be to configure and customize your application.
