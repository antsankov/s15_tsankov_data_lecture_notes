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

# Big Data/ NoSQL  

## Analytics use case 
* You can add workers to speed up processing. 
* You still need to add more DBs to support all of the nwe worker outputs. 
 * Partition your database across shards. Partition your data across these shards. 
 * You have to shut system off when you are resharding. 

* Even though you have sharded network, if one of the ndoes goes down then the entire system goes down as well. 

## Strategies 

* Make more complex replicators. 
* If everything fails immediately, it's good, we can fix it. If it's writing bad data, it might be difficuly to track down whats wrong. 
* Scaling application adds siginificantly more complexity. 
* 

## NoSQL to the rescue
* Horizontally scalable. 
* Manage sharding for you. 

## Types of NoSQL Databases
* Key-value 
* Graphs 
* Columnar 
* Documents

## Key-Value 
* When presented with a key it returs an arbitrarily large set of data, i.e. the value. 
* Stored like a Hash table 
* No query language, they act like a hash table. 
* Values are untyped, you can store any type of data in these databases. 
* Benefits: Simplicity 
* Examples: Amazo SimbpleDB, Redis (keeps everything in memory,used in cache), Voldemort, Riak.

## Graph Stores 
* Desgined to store graph structures rather than row column structures. 
* Difficult to shard. 
* This is NoSQL because it doesn't require a schema. 
* Exampels: Neo4J, Titan, Infinite Graph 

## Columnar Stores: 

* Able to scale to enormous amounts of data. 
* Able to achieve very fast writes. 
* also mainatins very fast read performance. 
* Basic Data Model: 
 * Column family, think of tis as the table of related data. 
 * Columns families consist of rows that have unique row keys. 
 * Rows consist of columns.
 * Columns consits of a key and a value. 
 * The value might be a json itself that in turn has a json map itself. 
* Hash tables all the way down. 

## DOcument Stores
* Like a key-value store but with more structure. 
* Insert documents. 
* Each document get indexed in a variety of ways, 
* Documents can be found via queries on any attribute. 
* Docuemnets can be grouped into collections, collections -> databases. 
* Each DB is then used by a parituclar applicatuion to get its work done. 
* Examples: MongoDB, CouchDB, Solr/Lucen. 

## Why NoSQL
* THere is no schema. 
* You can store anything you want in one of these databses. 
* 

# Couch DB 

## Document Databse 
* Document NoSQL Database
* built in Erland to support massic concurrency. 
* CouchDB's desgin embraces the web (RESTful API, high avaliability). 

## Document Model: 
* Self contained data 
* Each document contains everything that might be needed by an application that makes use of it. No foreign keys. Kind of like MongoDB 
* No schema is enforced. 
* Attributes can contian embedded documents. 

## CAP Theorem
Issues you have to confront when you have distributed servers: 
* Consistency: All clients see the same data. 
* Availability: All clients are able to read or write the data store when they want 
* Partition tolearance: A database can be split across multiple servers. 
YOU CAN ONLY PICK 2. 

## CAP Strategies: 
1. Consistency and Avaliblity: Relational DB only chooses Consistenct and availability. Low partitioon toleance. 
2. Avaliablilty and Partition Tolearnce: Provides the ability to scale horizontally and always be available for requests but can only guarantee eventual consitency. CouchDB does this. NoSQL optimizes for this. 
3. Consistency and Partition Tolearnce: Able to provide consistency at the price of not being available for reqeuests. 

## CouchDB 
* Uses B-tree that is map reduced. 
* Validaiton is done in JS. 
* Merge conflicts can occur, if it can't, it defers to the script. 

# MongoDB 
* Stores everything as documents
* Good for a read heavy environment 
* Index cardinality: number of possible values for an indexed field. 
 * You only want indices on high cardinality field. 
* Compound indices are hard, but they are necessary. 
* We can create a compund index that looks like this: ``` tweets,ensureIndex({'user.created_at':1, })```
* ```.explain("executionStats") ```
* Use $text to index text strings. 
* You cna use $geo for queries. 
* geojson.io to create polygons. 
 * First coordinate in your polygon is last point in polygon.

# Redis: 
- Really fast way to search Data. 
- With list, add it to head or tail in cosntant time. 
- Use sorted sets when accessing the middle. 
- Blocking operations allow server to notfy clients when they need the data. 
- You can cluster. 
- Runs with LUA scripting. 
- Not a database replacement. 

# Apache Kafka 
- Distributedm high throuhgput, distributed, fault tolerant, messaging system. 
- Kafka splits up data, and is dsitrbutred by ZookKeeper. 

# Memcahe
* Why use it instead of Redis? Easier to learn, more stable and more portable. 
*  Best in situations where the # of requests is high and the cost of generating data 

#Javascript 
* HOisting, javacript compiled first 
* Closure means we can return functions that have access to different variables. 
* Use scopes to hid data adnd export an object
* No classses, uses prototype inheritence. 
* ```this``` is not bound at compile time. 

# React 
* Maintains a virtual DOM  
* 
