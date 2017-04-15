## HTTP Requests

### How to Make a Request

In addition to using a web browser to request HTML documents, you can also use it to view raw data, most often in JSON or XML format.

In addition to using a web browser to request data, you can also request data using the command line, JavaScript, or any other contemporary server-side programming language like Ruby, Python, etc.

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

Send data to some URL. When you make a POST request, you need to send along the data in the body of the request. There are many ways to do this.

Using the command line:

```` sh
curl --data "name=testBot&description=testingTesting" https://southernct-443-robots-api.herokuapp.com/api/robots
# ... OR ...
curl -H "Content-Type: application/json" -X POST --data '{"name":"Test Bot", "description":"Posted via cURL."}' https://southernct-443-robots-api.herokuapp.com/api/robots
````

See [JavaScript AJAX Notes](/notes/javascript/ajax.md) for examples of how to make a POST request using JavaScript.
