Modern Cloud Computing
----------------------

>  To build Highly Scalable, highly available, resilient and dynamic applications

1. Hosting Evolution
2. Database Evolution
3. Application architecture evolution
4. High availability
5. Geo-Aware networks



Hosting evolution
-----------------

  > Nested Virtualization

   - Multiple VM's vs VM's inside VM

    - ![nested_virtualization](../images/cloud/nested_virtualization2.png)



   > Nested Virtualization

     - Modern hypervisors - highly scalable & performant
     - Abstracts the underlying hypervisor, networking & storage to easily leverage capacity from any cloud
      - ![nested_virtualization](../images/cloud/nested_virtualization.png)



   > Nested Virtualization

    - Automate the multi-VM environment. Eg: clone, snapshot, auto-deploy and self-service provision
    - Cost effective solution
    - ![nested_virtualization](../images/cloud/nested_virtualization1.png)
  



Hosting evolution
-----------------

  - Docker is an open-source project to easily create lightweight, portable, self-sufficient containers from any application. The same container that a developer builds and tests on a laptop can run at scale, in production, on VMs, bare metal, OpenStack clusters, public clouds and more.

![Dockers](../images/cloud/docker/docker1.png)



![Dockers](../images/cloud/docker/docker2.png)
  


![Dockers](../images/cloud/docker/docker3.png)



![Dockers](../images/cloud/docker/docker4.png)



![Dockers](../images/cloud/docker/docker5.png)



![Dockers](../images/cloud/docker/docker6.png)



![Dockers](../images/cloud/docker/docker8.png)



![Dockers](../images/cloud/docker/docker7.png)



Database Evolution
------------------

![Data](../images/cloud/nosql/nosql1.png)



Database Evolution
------------------

![Data](../images/cloud/nosql/nosql2.png)




Relational Databases
--------------------
 - data are stored in tables with typed columns 
 - all records in a table are homogenously structured and have the same columns and data types
 - tables are flat (no hierchical data in a table)
 - columns have primitive data types: multi-valued data are not supported
 - users are required to define the schema elements before data can be stored



Relational Databases
--------------------
 - inserted data must match the schema or the database will reject it
 - to get our data back, we need to read from multiple tables, either with or without joins 
 - to make multi-table (or other multi-record) operations behave predictably in concurrency situations 
 - relational databases provide transactions control over the ACID properties (atomicity, consistency, isolation, durability)



Relational Databases criticisms
-------------------------------
- lots of new databases have emerged in the past few years, 
  - often because object-relational mapping can be complex or costly
  - relational databases do not play well with dynamically structured data and often- varying schemas
  - overhead of SQL parsing and full-blown query engines may be significant for simple access patterns (primary key access, BLOB storage etc.)
  - scaling to many servers with the ACID guarantees provided by relational databases is hard




NoSQL databases
---------------

- provides alternative solutions for some of the mentioned problems
- NoSQL databases are generally non- relational, meaning they do not follow the relational model
- Sacrificing query languages, query planners, referential integrity, joins, ACID guarantees for cross-record operations etc.
- they do not provide tables with flat fixed- column records
- self- contained aggregates or even BLOBs 
- Easy migration and scaling



NoSQL - Access
-------------- 
> NoSQL database - Access
- NoSQL databases often provide simple interfaces to store and query data
- APIs offer access to low level data manipulation and selection methods
- protocols or HTTP REST APIs with JSON inside
- databases with HTTP APIs are web-enabled and can be run as internet-facing services



NoSQL - Distributed
------------------- 
- several NoSQL databases can be run in a distributed fashion, providing autoscalability and failover capabilities
- replication between distributed nodes is often lazy, meaning the database is eventually consistent
- Used as
  - document stores
  - key-value stores
  - wide column/column family stores
  - graph databases



NoSQL-Examples
--------------

````javascript

// NoSQL Object
{
  "id" : 1234,
  "name" : {
    "first" : "foo",
    "last" : "bar"
  },
  "topics": [
    "skating",
    "music"
  ]
}

````



NoSQL-Save
----------

- To store the user object, use save:

````javascript
//Save to mongoDB
mongo> db.user.save({
  "_id" : 1234,
  "name" : {
    "first" : "foo",
    "last" : "bar"
  },
  "topics" : [ "skating", "music" ]
});
````


NoSQL-Query
----------
- use find to filter on any attribute or subattribute(s):

````javascript

//Select
mongo> db.user.find({ 
  "_id" : 1234
});
mongo> db.user.find({ 
  "name.first" : "foo"
});

````


NoSQL-Query
----------

````javascript

//Select
mongo> db.user.find({ 
  "$or" : [ 
    { "name.first" : "foo"},
    { 
      "topics" : { 
        "$in" : [ "skating" ] 
      }
    }
  ]
});

````

NoSQL-MapReduce
---------------

- map-reduce is a general framework, present in many No-SQL databases.
- map-reduce requires at least a map function applied on each (changed) document to filter out irrelevant documents,
  and to emit data for all documents of interest
- it is actual programming, not writing queries!

> Filtering with map
````javascript
map = function (doc) {
  for (i = 0; 
       i < doc.topics.length; i++) {
    if (doc.topics[i] === 'music') {
      emit(null, doc);
      return; // done
    }
  }
};

````