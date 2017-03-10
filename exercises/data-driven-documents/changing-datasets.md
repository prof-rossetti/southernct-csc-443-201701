# Changing Datasets Exercise

Use JavaScript to manipulate the contents of a webpage to reflect information contained within a given data structure, then use an input element to update the information by changing the underlying dataset.

## Objectives

  1. Practice data-driven document development.
  * Practice updating page contents without refreshing the page.

## Prerequisites

  + [Data-driven Documents](/exercises/data-driven-documents/exercise.md)

## Instructions

Create a new `index.html` page and populate it with the following contents:

```` html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>Changing Datasets</title>
  </head>
  <body>
    <h1>Changing Datasets</h1>

    <select id="course-selector">
      <option value="443">Internet Programming</option>
      <option value="335">Database Management Systems Design</option>
    </select>

    <div id="my-container">
    </div>

    <script type="text/javascript">

      var myCourse = {name:"Internet Programming", url:"http://catalog.southernct.edu/undergraduate/courses/csc443.html"}

      var otherCourse = {name:"Database Management Systems Design", url:"http://catalog.southernct.edu/undergraduate/courses/csc335.html"}

      // manipulate the DOM here!

    </script>
  </body>
</html>
````

> NOTE: Do not at any time manually edit the HTML elements on this page. Only edit the contents of the `script` at the bottom of the page.

Preview the page in a browser.

In the console, use JavaScript to perform the following actions:

  1. Add an `a` element, nested inside an `h3` element, nested inside the `div#my-container` element.
  * Configure the text of the `a` element to display the name of the course (`myCourse`).
  * Configure the `a` element's `href` attribute to hyperlink to the course link (`myCourse`).
  * Configure the `select#course-selector` element such that when it's value is changed, the proper course is displayed (`myCourse` vs `otherCourse`).

Finally transcribe your JavaScript statements into the `script` at the bottom of the HTML page so the next time you load it, you should see your desired changes reflected.

> ## Further Exploration
>
> First, combine the `myCourse` object and the `otherCourse` object into a new array of objects. Assign this array to a variable called `courses`.
>
> Then, repeat the assignment instructions based on the structure of this new, unified, dataset.
>
> Hint: you may need to use array finding or filtering methods to select the proper dataset.
