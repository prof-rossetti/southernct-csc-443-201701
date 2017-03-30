## Asynchronous JavaScript (AJAX)

> AJAX stands for Asynchronous JavaScript and XML. In a nutshell, it is the use of the XMLHttpRequest object to communicate with server-side scripts. It can send as well as receive information in a variety of formats, including JSON, XML, HTML, and even text files. AJAX’s most appealing characteristic is its "asynchronous" nature which means it can communicate with the server, exchange data, and update the page all without having to refresh the browser.
>
> The two major features of AJAX allow you to do the following:
>
>  + Make requests to the server without reloading the page
>  + Receive and work with data from the server
> ...  - [Mozilla guide](https://developer.mozilla.org/en-US/docs/AJAX/Getting_Started)

Use AJAX to send and receive data between your client-side script and a server, all done without refreshing the page.

Be careful not to assume synchronous execution of your JavaScript code. Assume the time between request and response is not certain. Don't be surprised if you don't have access to the response variable within a global scope unless you pass it there from within the request function.

### How to Make an AJAX Request

Use vanilla JavaScript, jQuery, or d3 to make requests.

JavaScript `fetch()` Docs: https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API

jQuery `ajax()` Docs: http://api.jquery.com/jquery.ajax/

D3 `json()` Request Docs: https://github.com/d3/d3-request/blob/master/README.md#json

And more broadly, D3 `request()` Docs: https://github.com/d3/d3-request/blob/master/README.md#api-reference

#### GET

```` js
// todo: fetch()
````

```` js
// todo: $.ajax()
````

```` js
// todo: d3.json()
````

#### POST

```` js
// todo: fetch()
````

```` js
// todo: $.ajax()
````

```` js
/* todo: request
    .on("error", function(error) { callback(error); })
    .on("load", function(xhr) { callback(null, xhr); })
    .send(method, data);
*/
````
