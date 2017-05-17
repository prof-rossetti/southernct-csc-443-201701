
## Representational State Transfer (REST)

REST is essentially an Internet architecture paradigm whereby a client makes an HTTP Request to a server to send or receive a representation of one or more resources. The term "resource" generally refers to an instance of a class of object.

Developers of web services and APIs often design these applications to conform with RESTful architecture principles.

> One of the key characteristics of a RESTful Web service is the explicit use of HTTP methods in a way that follows the protocol as defined by RFC 2616. HTTP GET, for instance, is defined as a data-producing method that's intended to be used by a client application to retrieve a resource, to fetch data from a Web server, or to execute a query with the expectation that the Web server will look for and respond with a set of matching resources.
>
> REST asks developers to use HTTP methods explicitly and in a way that's consistent with the protocol definition. This basic REST design principle establishes a one-to-one mapping between create, read, update, and delete (CRUD) operations and HTTP methods. According to this mapping:
>  + To create a resource on the server, use POST.
>  + To retrieve a resource, use GET.
>  + To change the state of a resource or to update it, use PUT.
>  + To remove or delete a resource, use DELETE.
>
> ... - [IBM website ](https://www.ibm.com/developerworks/library/ws-restful/)

In practice, it is sometimes acceptable to use a POST request in place of a PUT or DELETE request. The idea is that GET requests are used for receiving data while the others are used for sending data or performing actions.

References:

  + https://www.ibm.com/developerworks/library/ws-restful/
  + http://www.restapitutorial.com/

### Typical API Endpoints

Here is an example of RESTful URL routes [used by](http://guides.rubyonrails.org/routing.html#crud-verbs-and-actions) the Ruby on Rails application framework given an example "photos" resource:

HTTP Verb | Path | Controller#Action | Used for
---	| ---	| ---	| ---
GET | /photos | photos#index | display a list of all photos
GET | /photos/new | photos#new | return an HTML form for creating a new photo
POST | /photos | photos#create | create a new photo
GET	| /photos/:id | photos#show | display a specific photo
GET	| /photos/:id/edit | photos#edit | return an HTML form for editing a photo
PATCH/PUT | /photos/:id | photos#update | update a specific photo
DELETE | /photos/:id | photos#destroy | delete a specific photo
