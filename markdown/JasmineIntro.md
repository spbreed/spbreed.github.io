What is Jasmine
----------------

> Jasmine is an automated testing framework for JavaScript.

- Each WebPage have set of functional DOM elements.
- Processes within a Web application are triggered by DOM events. 
- Button clicks, setting the focus on an element, document loading and any other event resulting from a user action or the browser. 
- Jasmine will provide methods to deal with DOM events.


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