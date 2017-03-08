## Document Object Model (DOM)

> "The Document Object Model (DOM) is a programming interface for HTML and XML documents. It provides a structured representation of the document and it defines a way that the structure can be accessed from programs so that they can change the document structure, style and content." - [Mozilla web docs](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model/Introduction)

Familiarize yourself with all of the following reference material:

  + [The HTML DOM Document Object](https://www.w3schools.com/jsref/dom_obj_document.asp)
  + [The HTML DOM Element Object](https://www.w3schools.com/jsref/dom_obj_all.asp)
  + [Using JavaScript to Manipulate the DOM](https://www.w3schools.com/js/js_htmldom_document.asp)

> "When an HTML document is loaded into a web browser, it becomes a document object."
> The document object provides properties and methods to access all node objects, from within JavaScript." - w3schools

```` js
window.document
document
````

```` js
document.URL
document.cookie

````

```` js
document.childNodes
document.children
document.children[0].children
````

### Page-loading

Observe lessons from https://prof-rossetti.github.io/js-dom-fundamentals/page-loading.html:

  + Compare the source code to messages logged to the browser's console.

### Selections

Reference: https://www.w3schools.com/js/js_htmldom_elements.asp.

Observe lessons from https://prof-rossetti.github.io/js-dom-fundamentals/selections.html:

  + Use JavaScript to programmatically select each element on the page.
  + Use JavaScript to select all child elements belonging to the `select#animal-selector` element.
  + Use JavaScript to identify the name of the currently-selected animal.

### Events

Reference: https://www.w3schools.com/js/js_htmldom_events.asp.

#### Event-listening

Reference: https://www.w3schools.com/jsref/met_document_addeventlistener.asp.

Observe lessons from https://prof-rossetti.github.io/js-dom-fundamentals/event-listening.html:

  + Use JavaScript to log a message or display an alert any time the button element is clicked.
  + Log a message or display an alert any time the select element is changed. Include the name of the currently-selected animal in the contents of the message/alert.

### DOM Manipulation

Again, reference: https://www.w3schools.com/js/js_htmldom_document.asp.

Observe lessons from https://prof-rossetti.github.io/js-dom-fundamentals/dom-manipulation.html:

  + Use JavaScript to change the contents of the message displayed on the page.
  + Use JavaScript to add and remove elements from the page. Try adding elements of many kinds. Try adding elements nested inside other elements.
