# protractor_sample_example
Reference: https://www.protractortest.org/#/

1.	What is the purpose to use  this tool?

Ans: Though Selenium can do some of the things what protractor does, the protractor is the industrial standard and best practice to test AngularJS applications. A Protractor can also manage multiple capabilities in it and handle the dynamic changes of web elements using ng-model, ng-click.., etc.. (Which selenium cannot do).

2.	Why this is better than other tool? Ans same as 1.

3.	Why you're using this tool? Ans same as 1.

4. Usability:

a. Normal scripting using page object and with different browsers. and platform e.g Windows, MAC, Mobile 
Ans: Protractor support Page Object Model. https://devonblog.com/continuous-delivery/protractor-functional-automation/
Protractor support Win, MAC and mobile app using Appium (not officially yet).

b. Parallel execution.
Ans: https://www.seleniumeasy.com/protractor-angularjs-tutorials/run-multiple-protractor-specs-in-parallel

c. Datadriven with Assertion using csv or xlsx Ans: https://devonblog.com/continuous-delivery/protractor-functional-automation/

d. Jenkins build or execution in Docker  Ans: Yes

e. Result Report: Jesmine, Mocha

f. Advantages and drawback

Ans: Drawback

a.	It supports only javascript.

b.	It runs very well in chrome browser. It don’t have much support on other browsers. It doesn't support latest version of Chrome on existing project. When I was running this tool, this tool supported till chrome V75 whereas V83 already available.
To resolve this issue, I have deleted 'proctractor' from C:\Users\ahoss1\AppData\Roaming\npm\node_modules and 'chromedriver' from C:\Users\ahoss1\AppData\Roaming\npm and re-install again and it worked! 

c.	If there is an issue with WebdriverJs, the Protractor team should wait for the WebDriverJs team to fix that issue. Protractor is built on webdriverJS. Protractor is not W3C standard.

d.	You cannot simulate real user (which is possible in selenium using robot class)

e.	Debugging in Protractor is a nightmare

f.	Could take some time to master all API and technicals if you are not from selenium background

g.	It does not have support to automate mobile Apps.

h.	Returning values is like going to the Moon

Tutorial: https://www.guru99.com/protractor-testing.html

#### Setup

npm install -g protractor

webdriver-manager update

webdriver-manager start

Create below js files:

todo-spec.js:

describe('angularjs homepage todo list', function() {
  it('should add a todo', function() {
    browser.get('https://angularjs.org');
  });
});

conf.js:

exports.config = {
  seleniumAddress: 'http://localhost:4444/wd/hub',
  specs: ['todo-spec.js']
};

Run the test: protractor conf.js

Please note: There is not package.json and node module exist in the project folder (except above 2 js files) since the proctractor, selenium server and chromedriver installed globally in NPM folder as part of proctractor installation.
