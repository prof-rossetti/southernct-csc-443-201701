## Asynchronous JavaScript (AJAX) - GET Requests

### Instructions

Create a new `index.html` page and populate it with the following contents:

```` html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>Fetching Data</title>
  </head>
  <body>
    <h1>Fetching Data</h1>

    <!-- LOAD JQUERY LIBRARY - ONLY NECESSARY FOR "FURTHER EXPLORATION" -->
    <script src="https://code.jquery.com/jquery-3.1.1.min.js" integrity="sha256-hVVnYaiADRTO2PzUGmuLJr8BLUSjGIZsDYGmIJLv2b8=" crossorigin="anonymous"></script>

    <!-- LOAD D3 LIBRARY - ONLY NECESSARY FOR "FURTHER EXPLORATION" -->
    <script src="https://d3js.org/d3.v4.min.js"></script>

    <script type="text/javascript">

      // FETCH THE DATA HERE!

    </script>
  </body>
</html>
````

From within the script at the bottom of the document, use JavaScript to fetch JSON data from [this URL](https://raw.githubusercontent.com/SCSU-CSC-Department/201701-csc-443-01/master/course.json) and log the results to the console.

Recognize you can't access the data from within the global scope. Practice accessing the data by passing it into the global scope or by inserting a `debugger` statement within the local scope of the function making the request.

> ## Further Exploration
>
> Use jQuery to fetch the data.
>
> Use D3 to fetch the data.
