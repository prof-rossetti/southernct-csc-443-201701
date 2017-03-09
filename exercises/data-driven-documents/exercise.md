# Data-driven DOM Manipulation

Use JavaScript to manipulate the contents of a webpage to reflect information contained within a given data structure.

## Objectives

  1. Gain exposure to data-driven document development.
  * Practice using JavaScript to manipulate the DOM.
  * Optionally practice using the jQuery library to manipulate the DOM.
  * Optionally practice using the D3 library to manipulate the DOM.

## Prerequisites

  + [DOM Exercise](/exercises/document-object-model/exercise.md)

## Instructions

Create a new `index.html` page and populate it with the following contents:

```` html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>My Data-driven Document</title>
  </head>
  <body>
    <h1>My Data-driven Document</h1>

    <div id="my-container">
      <p id="my-message">Some placeholder content.</p>
    </div>

    <!-- LOAD JQUERY LIBRARY - ONLY NECESSARY FOR "FURTHER EXPLORATION" -->
    <script src="https://code.jquery.com/jquery-3.1.1.min.js" integrity="sha256-hVVnYaiADRTO2PzUGmuLJr8BLUSjGIZsDYGmIJLv2b8=" crossorigin="anonymous"></script>

    <!-- LOAD D3 LIBRARY - ONLY NECESSARY FOR "FURTHER EXPLORATION" -->
    <script src="https://d3js.org/d3.v4.min.js"></script>

    <script type="text/javascript">

      var myCourse = {name:"Internet Programming", day:"Thursday", start_time:"7:05pm", end_time:"10:05pm"} // replace this placeholder JSON object with the full object from course.json (see below)

      // manipulate the DOM here!

    </script>
  </body>
</html>
````

> NOTE: Do not at any time manually edit the HTML elements on this page. Only edit the contents of the `script` at the bottom of the page.

Reference the [course.json](/course.json) file located in this repository's root directory. Copy its contents and paste them into the `script` at the bottom of the page, assigning it to the variable called `myCourse`.

Preview the page in a browser.

In the console, use JavaScript to perform the following actions:

  1. Change the placeholder text inside the `p#my-message` element from "Some placeholder content." to "My New Content!".
  * Remove the `p#my-message` element from the page altogether.
  * Add an `h3` element nested inside the `div#my-container` element to display the name of the course.
  * Add other elements as desired nested inside the `div#my-container` to display all information about the course. Include hyperlinks to all relevant external pages referenced by URL within the data structure.

Finally transcribe your JavaScript statements into the `script` at the bottom of the HTML page so the next time you load it, you should see your desired changes reflected.

> #### Further Exploration
>
> Replicate your HTML page twice. Within one of the copies, use jQuery instead of vanilla JavaScript to perform the DOM manipulations. Within the second copy, use the D3 library to perform the DOM manipulations.
>
> For jQuery DOM manipulation reference, see https://www.w3schools.com/jquery/jquery_dom_add.asp and https://www.w3schools.com/jquery/jquery_dom_remove.asp.
>
> For D3 DOM selection documentation, see https://github.com/d3/d3/blob/master/API.md#selecting-elements. For D3 DOM manipulation documentation, see https://github.com/d3/d3/blob/master/API.md#modifying-elements.
