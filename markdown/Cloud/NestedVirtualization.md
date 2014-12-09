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

  > Dockers
   - Docker is an open-source project to easily create lightweight, portable, self-sufficient containers from any application. The same container that a developer builds and tests on a laptop can run at scale, in production, on VMs, bare metal, OpenStack clusters, public clouds and more.

![Dockers](../images/cloud/docker/docker1.png)



![Dockers](../images/cloud/docker/docker2.png)
  


![Dockers](../images/cloud/docker/docker3.png)



![Dockers](../images/cloud/docker/docker4.png)



![Dockers](../images/cloud/docker/docker5.png)



![Dockers](../images/cloud/docker/docker6.png)



![Dockers](../images/cloud/docker/docker8.png)



![Dockers](../images/cloud/docker/docker9.png)



Database Evolution
------------------

![Data](../images/cloud/nosql/nosql1.png)



Database Evolution
------------------

![Data](../images/cloud/nosql/nosql2.png)




 > Relational Databases

 - data are stored in tables with typed columns 
 - all records in a table are homogenously structured and have the same columns and data types
 - tables are flat (no hierchical data in a table)
 - columns have primitive data types: multi-valued data are not supported
 - users are required to define the schema elements before data can be stored
 - inserted data must match the schema or the database will reject it
 - to get our data back, we need to read from multiple tables, either with or without joins 
 - to make multi-table (or other multi-record) operations behave predictably in concurrency situations 
 - relational databases provide transactions control over the ACID properties (atomicity, consistency, isolation, durability)



> Relational Databases criticisms

- lots of new databases have emerged in the past few years, 
  - often because object-relational mapping can be complex or costly
  - relational databases do not play well with dynamically structured data and often- varying schemas
  - overhead of SQL parsing and full-blown query engines may be significant for simple access patterns (primary key access, BLOB storage etc.)
  - scaling to many servers with the ACID guarantees provided by relational databases is hard




Database Evolution
------------------
> NoSQL databases

- provides alternative solutions for some of the mentioned problems
- NoSQL databases are generally non- relational, meaning they do not follow the relational model
- Sacrificing complex and costly features, such as  as query languages, query planners, referential integrity, joins, ACID guarantees for cross-record operations etc.
- they do not provide tables with flat fixed- column records
- instead, it is common to work with self- contained aggregates (which may include hierarchical data) or even BLOBs 
- Easy migration and scaling



Database Evolution
------------------
> NoSQL database - Access

- NoSQL databases are generally non- relational, meaning they do not follow the relational model
- this eliminates the need for complex object-relational mapping and many data normalisation requirements
- working on aggregates and BLOBs also led to sacrificing complex and costly features, such as query languages, query planners, referential integrity, joins, ACID guarantees for cross-record operations etc. in many of these databases
- they do not provide tables with flat fixed- column records 
- instead, it is common to work with self- contained aggregates (which may include hierarchical data) or even BLOBs

1. Selenium Server Configuration
2. Where your spec files are located
3. Browser capabilities required by spec files
4. The Base Url for your spec files
5. Jasmine Node Configuration



Example Configuration
---------------------

````javascript
// An example configuration file.
exports.config = {
  // Do not start a Selenium Standalone sever - only run this using chrome.
  chromeOnly: true,
  chromeDriver: 'node_modules/protractor/selenium/chromedriver',

  //baseURL

 // baseUrl: 'https://spbreed02.sharepoint.com/sites/appdev/_layouts/15/appredirect.aspx?instance_id={7000E10A-58A6-4668-AEDC-0B1FD6091280}',

  // Capabilities to be passed to the webdriver instance.
  capabilities: {
    'browserName': 'chrome'
  },

  // Spec patterns are relative to the current working directly when
  // protractor is called.
  specs: ['angularapp_spec.js'],

  // Options to be passed to Jasmine-node.
  jasmineNodeOpts: {
    showColors: true,
    defaultTimeoutInterval: 30000
    }

};
````



Running Test Scripts
--------------------

1. Create a NodeJS project in Visual Studio
2. Install protractor and update the web driver
3. Run the configuration file

````powershell 
#Run the sample configuration file 
node_modules\.bin\protractor chromeOnlyConf.js
````