# Lecture Notes for Data Engineering in Spring 2015

# Lecture 1

## Analytics
* Statistics is built on sampling, most of the info that we have is all there and doesn't requite sampling. 
* With Big Data we can be omnipotent and calculate the correct answer with 100% certainty.

## Storage 
* SQL is reliable and robust, but it isn't flexible. 
* SQL if you know the shcema of the data you are going to recive. 
* NoSQL is not good for doing arbitrary queries after the data has been input. 
  * Data modeling is wicked hard. 
* key-value stores, columnar stores, graph DB, etc. 

## InfoViz
* Twitter uses UTF-8
* Tools: D3, Tableau, R
* Collection -> Cleanup -> Storage -> Analysis -> Query/Vis

# Lecture 2 

##RESTful 

* Certain predefined commands ```get``` -read , ```post``` -create,```delete```-remove,```put``` -modify to interact with service.
* Page might load hundereds of different elements for every page. 
* W3C defines current spec for HTTP. 
* RE -> Representation/Resource : Ask for a resource, and have it given to you in a representation (HTML, XML, JSON) 
* S -> State

# Lecture 3 

## RESTful cont. 

* REST is better than SOAP most of the time. 
* To prevent a torrent of delete requests, we can use authentication 
 * Specifically OAUTH. 
*Types of Errors: 
 * 404 - nothing @ url.
 * 500 - the server choked. 
* Node is a wrapper around V8 chrome engine. 

## Testing

* Use rspec to test if the api works. 
* Test driven design. 

# Lecture 4 

* IMPORTANT LESSON: If you put computer to sleep with uncommited changes, you lose those changes... :(

# Lecture 5 

## Node

* Built on toop of Chrome V8. 
* Most code is packaged in a module. 
* Use anonymous functions as input for other functions. 
* Event loops are predfeined for you. 

# Lecture 6 

## Angular.js 

* Built on top of JS 

### Core concepts 
* Data binding - value of an HTML tag can be associated with a modle object. Change model based on HTML, change HTML based on Model 
* Controller - Are assocated with a portion of your HTML and define all state and methods that can be accessed with that section of the page. You can modularize your web app and decompose data into small chunks. 
* Servcies - controllers are used to manage some portion of a page while it is being displated. 
* If you need to maintain state between invocations of the controller you can create a service. Services exsit through life of application. 
* Directives are ubiquitous in Angular. They allow Angular to integrate into HTML in a natural way. 
* ALL OF THE TEMPLATING/CONTROLLER/ROUTING logic is on the client end. 
* Embeddable - can control as much or as little of the a web page as you specify. 
* Dependency Injection: I need an HTTP object. At run time it will create it when you need it. 
* Create aplication with a module. A module is a package of controllers. Ex: ```angular.module(['contactsApp',[])```
* Once you createa module you can gain a handle to call it by angular.module with no dependencies. 
* ```var self = this; ``` annything that is self is exported to view. 
* 

# Lecture 2/10/15

## Require.js

* Allows us to manage loading of different requirments for our angular module. 
* 

