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


