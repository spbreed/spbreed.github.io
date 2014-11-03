Testing Javacript Apps
----------------------

1. Modern Web Apps pre-dominantly use javascript
2. Multiple browsers
3. Flexible, Updatable and reusable code
4. Continous improvement



Testing frameworks
------------------

- Javascript Engines
  - Selenium
  - PhantomJS

- Languages
	- Jasmine
	- Mocha
	- QUnit



Jasmine Specification
---------------------

1. "Describe" defines  functional blocks
2. "It" describes  specification
3. "Expect" defines expectations

````javascript
describe('angularjs homepage', function() {
  it('should greet the named user', function() {
    browser.get('http://www.angularjs.org');

    element(by.model('yourName')).sendKeys('Julie');

    var greeting = element(by.binding('yourName'));

    expect(greeting.getText()).toEqual('Hello Julie!');
  });
````



Jasmine features
----------------

- Locating HTML
  -  element.By.className('redBtn')
  -	 element.By.css('.redBtn')
  -  element.By.id('loginButton')
  -  element.By.linkText('Go Home')
  -  etc

- Methods
  -	 clear()
  -  SendKeys()
  -  click()
  -  getLocation()
  -  etc