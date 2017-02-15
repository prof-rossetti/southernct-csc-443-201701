# Personal Website Checkpoint III: Interactivity

Using the Twitter Bootstrap front-end framework, configure interactive features as necessary to produce desired website functionality.

## Objectives

  1. Gain exposure to JavaScript within the context of Twitter Bootstrap.
  * Gain exposure to jQuery within the context of Twitter Bootstrap.
  * Configure internal and external JavaScript scripts.

## Prerequisites

  1. [Personal Website Checkpoint II: Style](projects/personal-website/checkpoints/style/checkpoint.md)
  * [CRUD Application Checkpoint II: Style](projects/crud-application/checkpoints/style/checkpoint.md)

## Instructions

In leveraging Twitter Bootstrap to design your personal website, you may have added one or more components which require JavaScript configuration to work properly (e.g. modals, dropdowns, buttons). You'll know if your components require additional configuration because the Twitter Bootstrap documentation will tell you so:

![a screenshot depicting Twitter Bootstrap documentation that says dropdowns can be made interactive with the corresponding javascript plugin, and provides a link to documentation for that plugin](heads-up.png)

### Setup

Regardless of whether or not this applies to you, you are encouraged to follow along using a new, separate project. Start by adding to it an `index.html` file, and paste in it the following contents:

```` html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>Bootstrap JS example</title>
    <!-- Use Twitter Bootstrap's CSS Stylesheet ... -->
    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css" integrity="sha384-BVYiiSIFeK1dGmJRAkycuHAHRg32OmUcww7on3RYdg4Va+PmSTsz/K68vbdEjh4u" crossorigin="anonymous">
  </head>
  <body>
    <div class="container">
      <h1>My Site</h1>
      <p class="lead">Hello World.</p>


      <!-- adapted from the Twitter Boostrap documentation on dropdowns ... -->
      <div class="dropdown">
        <button class="btn btn-default dropdown-toggle" type="button" id="dropdownMenu1" data-toggle="dropdown" aria-haspopup="true" aria-expanded="true">
          My Activities
          <span class="caret"></span>
        </button>

        <ul class="dropdown-menu" aria-labelledby="dropdownMenu1">
          <li><a href="activities/gaming.html">Gaming</a></li>
          <li><a href="activities/soccer.html">Soccer</a></li>
        </ul>
      </div>


    </div>
  </body>
</html>
````

Nothing new to see here, except for the `<div class="dropdown">` element and everything inside. This content was adapted from the [Twitter Bootstrap documentation on dropdown components](http://getbootstrap.com/components/#dropdowns).

On this page, you'll notice hyperlinks to two other pages: `activities/gaming.html` and `activities/soccer.html`. Let's create those other pages now, using with the following content:

```` html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>Gaming</title>
  </head>
  <body>
    <h1>A PAGE ABOUT GAMING!</h1>
  </body>
</html>
````

```` html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>Soccer</title>
  </head>
  <body>
    <h1>A PAGE ABOUT SOCCER!</h1>
  </body>
</html>
````

Start up a local web server to preview your site in a browser.

![an animated gif demonstrating this site's functionality at this stage in the development process. all pages are viewable by visiting their respective URLs, but the home page links to the activity pages are not visible, and nothing happens when the dropdown button is clicked.](step-1.gif)

You'll notice the dropdown button is visible, but not working as desired.

To make it work, we need to first configure it using JavaScript.

Don't worry if JavaScript is new to you. We will cover it in greater depth in subsequent weeks. But for right now, all we need to know how to do is follow the instructions provided at http://getbootstrap.com/javascript/.

### External Script

### Internal Script
