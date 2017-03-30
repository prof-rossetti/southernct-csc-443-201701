## Asynchronous JavaScript (AJAX)

> AJAX stands for Asynchronous JavaScript and XML. In a nutshell, it is the use of the XMLHttpRequest object to communicate with server-side scripts. It can send as well as receive information in a variety of formats, including JSON, XML, HTML, and even text files. AJAX’s most appealing characteristic is its "asynchronous" nature which means it can communicate with the server, exchange data, and update the page all without having to refresh the browser.
>
> The two major features of AJAX allow you to do the following:
>
>  + Make requests to the server without reloading the page
>  + Receive and work with data from the server
> ...  - [Mozilla guide](https://developer.mozilla.org/en-US/docs/AJAX/Getting_Started)

Use AJAX to send and receive data between your client-side script and a server, all done without refreshing the page.

Be careful not to assume synchronous execution of your JavaScript code. Assume the time between request and response is not certain.

Don't be surprised if you don't have access to the response variable within the global scope unless you pass it there from within the request function. For more information on global vs local scopes, see [this guide](https://www.w3schools.com/js/js_scope.asp).

### How to Make an AJAX Request

Use vanilla JavaScript, jQuery, or d3 to make requests. Some libraries offer shortcut/alias methods specifically used for making GET requests for JSON data.

JavaScript:

  + General `fetch()` Docs: https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API

jQuery:

  + General `$.ajax()` Docs: http://api.jquery.com/jquery.ajax/
  + Specific `$.getJSON()` Docs: http://api.jquery.com/jquery.getjson/

D3:

  + General `d3.request()` Docs: https://github.com/d3/d3-request/blob/master/README.md#api-reference
  + Specific `d3.json()` Request Docs: https://github.com/d3/d3-request/blob/master/README.md#json

#### GET

```` js
//
// Vanilla JavaScript
//

var url = "https://raw.githubusercontent.com/SCSU-CSC-Department/201701-csc-443-01/master/course.json"

fetch(url)
  .then(function(response) {
    console.log("GOT A RESPONSE:", response)

    response.json()
      .then(function(json){
        console.log("GOT SOME DATA:", json)
        // DO SOMETHING WITH THE DATA HERE!
      })
  })
  .catch(function(err){
    console.log("GOT AN ERROR:", err)
  }) // handle errors
````

```` js
//
// jQuery
//

var url = "https://raw.githubusercontent.com/SCSU-CSC-Department/201701-csc-443-01/master/course.json"

$.getJSON(url, function(json) {
  console.log("GOT SOME DATA:", json)
  // DO SOMETHING WITH THE DATA HERE!
});
````

```` js
//
// D3
//

var url = "https://raw.githubusercontent.com/SCSU-CSC-Department/201701-csc-443-01/master/course.json"

d3.json(url, function(json){
  console.log("GOT SOME DATA:", json)
  // DO SOMETHING WITH THE DATA HERE!
})

````

#### POST

TBA

```` js
// TBA - fetch()
````

```` js
// TBA -  $.ajax()
````

```` js
// TBA - d3.request()
````
