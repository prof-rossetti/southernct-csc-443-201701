# CRUD Application Checkpoint V: Application Navigation

Establish the routing and navigational structure of your application.

## Objectives

  1. Gain familiarity with Express application navigation, including routers and views.
  2. Practice developing the structure of a web application.

## Prerequisites

  1. [CRUD Application Checkpoint IV: Application Generation](/projects/crud-application/checkpoints/app-generation/checkpoint.md)

## Instructions

### Routing

Notice in the `app.js` file the inclusion of two local modules:

    var index = require('./routes/index');
    var users = require('./routes/users');

These modules define the application's routing logic. Examine the `routes/index.js` file:

```` js
var express = require('express');
var router = express.Router();

/* GET home page. */
router.get('/', function(req, res, next) {
  res.render('index', { title: 'Express' });
});

module.exports = router;
````

There's a lot going on in so few lines of code, so let me provide some commentary:

```` js
var express = require('express'); // loads the "express" module from the node_modules directory
var router = express.Router(); // initializes a new router object (see https://expressjs.com/en/api.html#router for documentation)

/* GET home page. */
// this .get() function enables the application's web server to handle a GET request
// ... to the url path indicated by the first parameter, in this case '/'.
// ... The second parameter is a function to be invoked when a GET request is made at the specified url path.
// ... The callback function's first two parameters represent a request object and a response object.
router.get('/', function(req, res, next) {
  res.render('index', { title: 'Express' }); // calls the .render() function on the response object ...
  // ... instructing the response to render a "view" file indicated by the first parameter ...
  // ... and pass into it some custom data specified in the second parameter, which is an object.
});

module.exports = router; // enables other modules to load this one, and specifies the variable to load when this module is required
````

You don't have to internalize all of this at the moment. But what you can do is tweak the value of the `title` string, changing it from `'Express'` to something like 'My CRUD App'. Refresh the browser and see what happens:

![a screenshot of the application's homepage which includes a heading of "My CRUD App" and a subheading of "Welcome to My CRUD App"](passing-data-to-a-view.png)

### Viewing

Congratulations, you have just passed some custom data from the `routes/index.js` file into the view file defined at `views/index.ejs`. Examine the `views.ejs` file to see how that data is getting used.

```` html
<!DOCTYPE html>
<html>
  <head>
    <title><%= title %></title>
    <link rel='stylesheet' href='/stylesheets/style.css' />
  </head>
  <body>
    <h1><%= title %></h1>
    <p>Welcome to <%= title %></p>
  </body>
</html>
````

It comes as no surprise that this view file is making use of the `title` variable that was passed to it. In the same way we can pass static data from our routers to our views, we can pass resources to fulfill the promise of our CRUD application.

Before we move on, take a moment to notice this "view" file. It looks a lot like HTML. It is HTML. Well, most of it. All of the code except for a few blocks which are encapsulated inside these special tags: `<%= ... %>`. This syntax is part of the magic of the EJS view engine that we configured when we first initialized our application. It executes any JavaScript code inside these tags and outputs the resulting HTML. Super cool, right? It's clear to see why EJS stands for "Embedded JavaScript."

#### More Views

Navigate to http://localhost:3000/users in your browser. Notice there is also content on that page that is getting passed from the router defined in `routes/users.js`. But this time, there is no corresponding view file - the router is passing data directly to the browser via the `send()` function.

![a screenshot of the application's homepage which includes a heading of "My CRUD App" and a subheading of "Welcome to My CRUD App"](passing-data-to-the-browser.png)

Good to know. Instead of a message string, try passing a JSON object to the `res.send()` function, like `res.send({a:1, b:2, c:3})`.

If you're curious, try to add a link from the index page to the users page. Hint: it is as simple as editing the HTML code in the `views/index.ejs` file.

Then feel free to delete the `routes/users.js` file because we don't need it. If you do, also remove, or comment-out the lines `var users = require('./routes/users');` and `app.use('/users', users);` from the `app.js` file. Then restart the web server and notice what happens when you try to navigate back to the users page:

![a 404 (Not Found) error](404-not-found.png)

### New Views

You can add new routers and views in the opposite manner that you just deleted the last one. First, make sure to add a line like `var users = require('./routes/users');` near the top of the `app.js` file. This loads the router logic and makes it available for further use by the application. Next, make sure to add a line like `app.use('/users', users);` in the appropriate part of `app.js` file. This associates the router logic with a given URL path (I'd recommend always anchoring your routers to the root url "/"). Finally, create a new router file and optionally a new view file at the specified file paths, and configure them to match the prior examples.

Your mission is now to adapt and expand this application's routers and views to include a robots index page and a robot show page. First start by passing static hard-coded data from the router to the view. After you configure the routers and views to display static data, commit your code, then attempt to issue GET requests to fetch data from the provided API and pass that dynamic data back to the view. If you are able to configure your routers to request data from the API and display the results on the page, you have succeeded in your mission!

#### Displaying Static Data

Setup your routers to pass example data to their corresponding views.

##### Routers

Create a robots router named `routes/robots.js` and paste in contents like the following:

```` js
var express = require('express');
var router = express.Router();

var myRobots = [
  {
    "_id":"123abc",
    "name":"r2d2",
    "description":"holds a secret message",
    "in_stock":100
  },
  {
    "_id":"456def",
    "name":"bb8",
    "description":"rolls around",
    "in_stock":75
  },
  {
    "_id":"789xyz",
    "name":"c3po",
    "description":"specializes in language translation",
    "in_stock":50
  }
] // static hard-coded data (for example)

/* List Robots */

router.get('/robots', function(req, res, next) {
  console.log("LISTING ROBOTS", myRobots) // use static hard-coded data for now
  res.render('robots/index', {robots: myRobots, title: "All Robots"});
});

/* Show Robot */

router.get('/robots/:id', function(req, res, next) {
  var robotId = req.params.id;
  var robot = myRobots.find(function(robot){ return robot._id == robotId }) // use static hard-coded data for now

  if (robot) {
    console.log("SHOWING ROBOT", robot)
    res.render('robots/show', {robot: robot, title: `Robot ${robotId}`});
  } else {
    var errorMessage = `OOPS - COULDN'T FIND ROBOT ${robotId}`
    console.log(errorMessage)
    res.send(errorMessage)
  }
});

module.exports = router;
````

Also configure your `app.js` file to use this robots router, anchoring its URLs relative to the root url ("/").

Visit http://localhost:3000/robots to find an error about a missing view. We will add those now.

##### Views

Add two new view files at `views/robots/index.ejs` and `views/robots/show.ejs`, respectively.

In the index view, paste in contents like the following:

```` html
<!DOCTYPE html>
<html>
  <head>
    <title><%= title %></title>
    <link rel='stylesheet' href='/stylesheets/style.css' />
  </head>
  <body>
    <h1><%= title %></h1>

    <ul>
      <% robots.forEach(function(robot){ %>
        <li><%= robot._id %> - <%= robot.name %> - <%= robot.description %></li>
      <% }); %>
    </ul>

  </body>
</html>
````

Nothing new here, except we are looping through each robot passed to the view, and adding a corresponding list item to the list.

> EJS Note: Notice the difference in EJS tags (`<%= ... %>` vs `<% ... %>`), where the former version, the one with the equals sign, "outputs the value into the template", and the latter, the "scriptlet" tag without an equals sign, is used for control flow. For more information see [EJS Docs](http://ejs.co/).

In the show view, paste in contents like the following:

```` html
<!DOCTYPE html>
<html>
  <head>
    <title><%= title %></title>
    <link rel='stylesheet' href='/stylesheets/style.css' />
  </head>
  <body>
    <h1><%= title %></h1>

    <p><%= robot.name %> - <%= robot.description %></p>

  </body>
</html>
````

This is a simple view which makes use of the robot object passed to it.

Visit http://localhost:3000/robots again to see a list of robots on that page. Copy and paste one of the robot's identifiers into the browser to visit that robot's show page. Verify you see the robot's information on its corresponding show page.

You may need to restart your web server to recognize the new files.

Commit your changes to version control because you have reached a milestone in this checkpoint exercise.

#### Displaying Dynamic Data

It's time to replace our placeholder robots data with real data returned from the Robots API Server.

Pick your favorite way of making client-side GET requests, and use that same library to make GET requests on the server-side. First install the respective third-party NPM module:

```` sh
# If you prefer fetch():
npm install node-fetch --save # https://www.npmjs.com/package/node-fetch

# If you prefer d3:
npm install d3 --save # https://www.npmjs.com/package/d3

# If you prefer jQuery:
npm install jquery --save # https://www.npmjs.com/package/jquery
````

Update the robots router to utilize the chosen method of issuing GET requests. If you chose `fetch()`, your router might look like this:

```` js
var express = require('express');
var router = express.Router();
var fetch = require('node-fetch');

/* List Robots */

router.get('/robots', function(req, res, next) {
  var url = "https://southernct-443-robots-api.herokuapp.com/api/robots.json"

  fetch(url)
    .then(function(response) {
      response.json()
        .then(function(json){
          console.log("LISTING ROBOTS", json)
          res.render('robots/index', {robots: json, title: "All Robots"});
        })
    })
    .catch(function(err){
      console.log("GOT AN ERROR:", err)
      res.send({error: `OOPS - SERVER ERROR ${err}`});
    })
});

/* Show Robot */

router.get('/robots/:id', function(req, res, next) {
  var robotId = req.params.id;
  var errorMessage = `OOPS - COULDN'T FIND ROBOT ${robotId}`
  var url = `https://southernct-443-robots-api.herokuapp.com/api/robots/${robotId}.json`

  fetch(url)
    .then(function(response) {
      response.json()
        .then(function(json){
          console.log("SHOWING ROBOT", json)
          res.render('robots/show', {robot: json, title: `Robot ${robotId}`});
        })
        .catch(function(err){
          console.log("JSON PARSE ERROR", err)
          res.send(errorMessage)
        })
    })
    .catch(function(err){
      console.log(errorMessage)
      res.send(errorMessage)
    })
});

module.exports = router;
````

When you are finished, you should be able to view the index page and show page in the browser. And when you do, there you should see real data from the API.































> ### Further Exploration
>
> If your application contains duplicate code across at least two of its views, DRY-up that shared code, you can abstract-away any shared HTML content into a separate file called a "view partial" or a "template", and include it via an EJS snippet like `<% include path/to/template %>`. See https://github.com/tj/ejs#includes for documentation.
>
> Congrats, you are making life easier on yourself and preventing future effort and error by DRY-ing up much of that shared HTML code.
