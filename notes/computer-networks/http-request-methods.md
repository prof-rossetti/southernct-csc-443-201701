## HTTP Requests

### How to Make a Request

In addition to using a web browser to request HTML documents, you can also use it to view raw data, most often in JSON or XML format.

You can also make web requests using most contemporary server-side programming languages like Ruby, Python, etc.

  + Browser
  + cURL
  + JavaScript `fetch()`
  + etc.

### Request Methods

W3Schools: https://www.w3schools.com/tags/ref_httpmethods.asp

#### GET

Request some data from some URL.

Using the command line:

```` sh
curl https://raw.githubusercontent.com/SCSU-CSC-Department/201701-csc-443-01/master/course.json
````

See [JavaScript AJAX Notes](/notes/javascript/ajax.md) for examples of how to make a GET request using JavaScript.

#### POST

Send data to some URL. When you make a POST request, you need to send along the data in the body of the request.

Using the command line:

```` sh
# TBA - curl example
````

See [JavaScript AJAX Notes](/notes/javascript/ajax.md) for examples of how to make a POST request using JavaScript.
