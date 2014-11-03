How it Works
-------------

1. Runs on NodeJS server
2. Protractor uses WebDriver API to send test cases to Web Server
3. Web Server interpretter compiles it down to JSON and passed it to browser
![Protactor](../images/components.png)



Installation
------------

1. [Install NodeJS server](http://nodejs.org/download/) 
2. ![Windows](../images/NodeJS_Install.png)
3. Install Protractor via Node Package Manager (NPM) (This is similar to NUGET)
4. Install Selenium Server and update Web-Driver
	
````powershell  
# Install protractor from NPM. Run this on the node project folder
npm install protractor --save-dev

#Run this from the project folder to update web driver
node_modules\.bin\webdriver-manager update
````



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