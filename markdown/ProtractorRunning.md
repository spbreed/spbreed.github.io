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
4. Install Selenium Server
	
````powershell  
npm install protractor --save-dev
.bin\webdriver-manager update
````



Running Test Scripts
--------------------

1. 