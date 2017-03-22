## Document Object Model (DOM)

> "The Document Object Model (DOM) is a programming interface for HTML and XML documents. It provides a structured representation of the document and it defines a way that the structure can be accessed from programs so that they can change the document structure, style and content." - [Mozilla web docs](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model/Introduction)

Familiarize yourself with all of the following reference material:

  + [The HTML DOM Document Object](https://www.w3schools.com/jsref/dom_obj_document.asp)
  + [The HTML DOM Element Object](https://www.w3schools.com/jsref/dom_obj_all.asp)
  + [Using JavaScript to Manipulate the DOM](https://www.w3schools.com/js/js_htmldom_document.asp)

> "When an HTML document is loaded into a web browser, it becomes a document object." - w3schools

```` js
window.document
document
````

```` js
document.URL
document.cookie

````

> The document object provides properties and methods to access all node objects, from within JavaScript." - w3schools

```` js
document.childNodes
document.children
document.children[0].children
````

### Selections

Reference: https://www.w3schools.com/js/js_htmldom_elements.asp.

```` js
// document.getElementById()
// document.getElementsByTagName()
// document.getElementsByClassName()
// document.querySelectorAll()
````

### Events

Reference: https://www.w3schools.com/js/js_htmldom_events.asp.

#### Event-listening

Reference: https://www.w3schools.com/jsref/met_document_addeventlistener.asp.

```` js
// document.addEventListener()
````

### DOM Manipulation

Again, reference: https://www.w3schools.com/js/js_htmldom_document.asp.
