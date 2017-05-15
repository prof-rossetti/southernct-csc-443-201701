# CRUD Application Checkpoint VII - Reading Records

## Objectives

  1. Gain exposure to modifying the routing logic of an Express web application.
  2. Practice passing data from an Express router and using it in a view.
  3. Practice agile, iterative software development techniques.
  4. Practice issuing GET requests.

## Prerequisites

  1. [CRUD Application Checkpoint VI: Navigation and Routing](/projects/crud-application/checkpoints/app-navigation/checkpoint.md)

## Instructions

Your mission is now to adapt and expand this application's routers and views to include a robots index page and a robot show page. First start by passing static hard-coded data from the router to the view. After you configure the routers and views to display static data, commit your code, then attempt to issue GET requests to fetch data from the provided API and pass that dynamic data to the view. If you are able to configure your routers to request data from the API and display the results on the page, you have succeeded in your mission!

### Adding and Removing Views

Feel free to delete the `routes/users.js` file because we don't need it. If you do, also remove, or comment-out the lines `var users = require('./routes/users');` and `app.use('/users', users);` from the `app.js` file. Then restart the web server and notice a 404 error that results from trying to navigate back to the users page. That's to be expected, as we removed that routing logic from our application.

You can add new routers and views in the opposite manner that you just deleted the last one. First, make sure to add a line like `var users = require('./routes/users');` near the top of the `app.js` file. This loads the router logic and makes it available for further use by the application. Next, make sure to add a line like `app.use('/', users);` in the appropriate part of `app.js` file. This associates the router logic with a given URL path (I'd recommend always anchoring your routers to the root url "/"). Finally, create a new router file and optionally a new view file at the specified file paths, and configure them to match the prior examples.

#### Displaying Static Data

Setup your routers to pass example data to their corresponding views.

##### Routers

Create a new "robots" router named `routes/robots.js` and paste in contents like the following:

```` js
var express = require('express');
var router = express.Router();

var myRobots = [
  {"_id":"123abc", "name":"r2d2", "description":"holds a secret message", "in_stock":100},
  {"_id":"456def", "name":"bb8", "description":"rolls around", "in_stock":75},
  {"_id":"789xyz", "name":"c3po", "description":"specializes in language translation", "in_stock":50}
] // static hard-coded data (for example)

/* List Robots */

router.get('/robots', function(req, res, next) {
  console.log("LISTING ROBOTS", myRobots)
  res.render('robots/index', {robots: myRobots, title: "All Robots"});
});

/* Show Robot */

router.get('/robots/:id', function(req, res, next) {
  var robotId = req.params.id;
  var robot = myRobots.find(function(robot){ return robot._id == robotId })

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

Also configure your `app.js` file to use this robots router, anchoring its URLs relative to the root url ("/") by adding the two lines of code mentioned in the "New Views" section of this checkpoint exercise.

Visit http://localhost:3000/robots to encounter an error complaining about a missing view. Don't worry, we will add the views now.

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

Awesome job. Commit your changes to version control because you have reached a significant milestone in this checkpoint exercise.

#### Displaying Dynamic Data

It's time to replace our placeholder robots data with real data returned from the provided web service.

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
  var url = "https://southernct-443-robots-api.herokuapp.com/api/robots"

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
  var url = `https://southernct-443-robots-api.herokuapp.com/api/robots/${robotId}`

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

Notice we are invoking `res.send()` or `res.render()` from within the local scope of the request functions.

When you are finished, you should be able to view the index page and show page in the browser. And when you do, there you should see real data from the API.

Nice job. You are more than half-way finished with developing this application. Commit your changes to version control.































> ### Further Exploration
>
> As you continue to create and develop additional views, you will most likely end up using shared HTML code such as navigation and footer links. If your application contains duplicate code across at least two of its views, DRY-up that shared code by abstracting-away any shared HTML content into a separate file called a "view partial" or a "template", and include it via an EJS snippet like `<% include path/to/template %>`. See https://github.com/tj/ejs#includes for documentation.
>
> Congrats, you are making life easier on yourself and preventing future effort and error by DRY-ing up much of that shared HTML code.
