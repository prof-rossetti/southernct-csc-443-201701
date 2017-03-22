## Window

Reference https://www.w3schools.com/jsref/obj_window.asp.

Get current browser window dimensions:

```` js
window.innerHeight
window.innerWidth
````

Get information about the URL of the current page:

```` js
window.location
window.location.href
window.location.protocol
window.location.host
window.location.port
window.location.pathName
window.location.toString()
````

Store data:

```` js
window.localStorage //=> Storage {length: 0}
window.localStorage.userID = "ABCD"
window.localStorage //=> Storage {userID: "ABCD", length: 1}
````

##### Alerts

Display a pop-up alert message box:

```` js
window.alert("HELLO WORLD")

alert("HELLO WORLD")
````

##### Timeouts

Invoke a function after waiting for a specified duration of time:

```` js
function doStuff() {
  console.log("PATIENTLY WAITING")
}

doStuff()

window.setTimeout(doStuff, 5000); // invoke the doStuff() function after waiting 5 seconds

setTimeout(doStuff, 5000);
````

##### Intervals

Invoke a function at specified intervals:

```` js
function doStuff() {
  console.log("DOING IT AND DOING IT AND DOING IT WELL")
}

window.setInterval(doStuff, 1000); // invoke the doStuff() function once per second

setInterval(doStuff, 1000);
````

Stop intervals:

```` js
function doStuff() {
  console.log("DOING IT AND DOING IT AND DOING IT WELL")
}

var myInterval = window.setInterval(doStuff, 500); // must store the interval in a variable to access it later

clearInterval(myInterval);
````

> #### Further Exploration
>
> Use JavaScript to log or display the current dimensions (height and width) of the browser window one or more times per second. Resize the window to verify the values change. Next, include the current time of day in the logs as well.
>
> Finally, see if you can create an auto-updating "clock" whereby the current time is always displayed on a page.
