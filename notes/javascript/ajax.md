## Asynchronous JavaScript (AJAX)

> AJAX stands for Asynchronous JavaScript and XML. In a nutshell, it is the use of the XMLHttpRequest object to communicate with server-side scripts. It can send as well as receive information in a variety of formats, including JSON, XML, HTML, and even text files. AJAX’s most appealing characteristic is its "asynchronous" nature which means it can communicate with the server, exchange data, and update the page all without having to refresh the browser.
>
> The two major features of AJAX allow you to do the following:
>
>  + Make requests to the server without reloading the page
>  + Receive and work with data from the server
>
> ... - [Mozilla website](https://developer.mozilla.org/en-US/docs/AJAX/Getting_Started)

Use AJAX to send and receive data between your client-side script and a server, all done without refreshing the page.

Be careful not to assume synchronous execution of your JavaScript code. Assume the time between request and response is not certain.

Don't be surprised if you don't have access to the response variable within the global scope unless you pass it there from within the request function. For more information, refer to this guide on [global vs local scopes](https://www.w3schools.com/js/js_scope.asp).

### How to Make an AJAX Request

Use vanilla JavaScript, jQuery, or d3 to make requests. Some libraries offer shortcut/alias methods specifically used for making GET requests for JSON data.

JavaScript:

  + General `fetch()` Docs: https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API.

jQuery:

  + General `$.ajax()` Docs: http://api.jquery.com/jquery.ajax/.
  + Specific `$.getJSON()` Docs: http://api.jquery.com/jquery.getjson/.
  + Specific `$.post()` Docs: https://api.jquery.com/jquery.post/.
  + Parsing responses: https://api.jquery.com/jQuery.ajax/#jqXHR.

D3:

  + General `d3.request()` Docs: https://github.com/d3/d3-request/blob/master/README.md#api-reference.
  + Specific `d3.json()` Request Docs: https://github.com/d3/d3-request/blob/master/README.md#json.

#### GET

Using vanilla JavaScript:

```` js
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

Using jQuery:

```` js
var url = "https://raw.githubusercontent.com/SCSU-CSC-Department/201701-csc-443-01/master/course.json"

$.getJSON(url, function(json) {
  console.log("GOT SOME DATA:", json)
  // DO SOMETHING WITH THE DATA HERE!
});
````

Using D3:

```` js
var url = "https://raw.githubusercontent.com/SCSU-CSC-Department/201701-csc-443-01/master/course.json"

d3.json(url, function(json){
  console.log("GOT SOME DATA:", json)
  // DO SOMETHING WITH THE DATA HERE!
})

````

#### POST

Using vanilla JavaScript:

```` js
var requestUrl = "https://southernct-443-robots-api.herokuapp.com/api/robots"
var formData = {name: "New Bot", description: "Does all the things."}
var requestOptions = {
  method: "POST",
  headers: {'Accept':'application/json', 'Content-Type':'application/json'},
  body: JSON.stringify(formData)
}

fetch(requestUrl, requestOptions)
  .then(function(response) {
    if (response.ok) { // check response status and proceed accordingly
      response.json()
        .then(function(json){
          // HANDLE RESPONSE DATA HERE
        })
    } else {
      // HANDLE RESPONSE ERRORS HERE
    }
  })
  .catch(function(err){
    // HANDLE FETCH ERRORS HERE
  })
````

Using jQuery:

```` js
var requestUrl = "https://southernct-443-robots-api.herokuapp.com/api/robots"
var formData = {name: "New Bot", description: "Does all the things."}

$.post(requestUrl, formData)
  .done(function(data, textStatus, xhr) {
    // HANDLE RESPONSE HERE
  })
  .fail(function(xhr, textStatus, errorThrown){
    // HANDLE ERRORS HERE
  })

````

Using D3:

```` js
var requestUrl = "https://southernct-443-robots-api.herokuapp.com/api/robots"
var formData = {name: "New Bot", description: "Does all the things."}

d3.request(requestUrl)
  .header("Accept", "application/json")
  .header("Content-Type", "application/json")
  .on("error", function(error) {
    // HANDLE ERRORS HERE
  })
  .on("load", function(xhr) {
    // HANDLE RESPONSE HERE
  })
  .send("POST", JSON.stringify(formData))

````
