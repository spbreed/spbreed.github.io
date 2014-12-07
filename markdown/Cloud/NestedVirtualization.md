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
   - Modern hypervisors are highly scalable and high performant
    - Abstracts the underlying hypervisor, networking & storage to easily leverage capacity from any cloud
    - Automate the multi-VM environment. Eg: clone, snapshot, auto-deploy and self-service provision
    - Cost effective solution
  ![nested_virtualization](../images/cloud/nested_virtualization.png)
  



Hosting evolution
-----------------

  > Dockers
   - Multiple VM's vs VM's inside VM
   - Modern hypervisors are highly scalable and high performant
    - Abstracts the underlying hypervisor, networking & storage to easily leverage capacity from any cloud
    - Automate the multi-VM environment. Eg: clone, snapshot, auto-deploy and self-service provision
    - Cost effective solution
  ![nested_virtualization](../images/cloud/nested_virtualization.png)
  



Configuration
-------------

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