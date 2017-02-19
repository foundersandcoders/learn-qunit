# Learn QUnit

A quick introduction to JavaScript unit testing with QUnit.js.

## What is testing?  

**Testing** is a process of executing a program or application with the intent of finding the **bugs**.

It can also be stated as the process of **validating** and **verifying** that a software program or application:  
- meets the business and technical requirements that guided it’s design and development
- works as expected
- can be implemented with the same characteristic.

Testing is necessary because we all make mistakes. Some of those mistakes are unimportant, but some of them are expensive or dangerous. We need to check everything and anything we produce because things can always go wrong.

## What is unit testing?  

**Unit testing** is a process of testing certain **functions** and areas – or units – of our code. This gives us the ability to verify that our _functions work as expected_.

![Testing layers](https://media.licdn.com/mpr/mpr/p/8/005/099/219/08c5a55.jpg)

Writing solid unit tests and well-tested code:

- helps improve the quality of the code
- breaks down a problem and code into small manageable pieces that can be reusable in other parts of the application
- can prevent future changes from breaking functionality.

## What is Qunit?

The official description on http://qunitjs.com/ is:

> QUnit is a powerful, easy-to-use JavaScript unit testing framework.
  It's used by the jQuery, jQuery UI and jQuery Mobile projects and is capable of testing any generic JavaScript code.

### Assertions

The **equal** assertion uses the simple comparison operator (**==**) to compare the actual and expected arguments.
When they are equal, the assertion passes; otherwise, it fails.

**equal( actual, expected [, message ] )**

Example:

```javascript
QUnit.test( "equal test", function (assert) {
  assert.equal( 0, 0, "Zero, Zero; equal succeeds" );
});
```

### Setup

To use QUnit, you only need to include two QUnit files on your HTML page.   
QUnit consists of  **qunit.js**, the test runner and testing framework, and **qunit.css**, which styles the test suite page to display test results.

**The contents of test/qunit.html:**

```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width">
  <title>QUnit Example</title>
  <link rel="stylesheet" href="https://code.jquery.com/qunit/qunit-2.1.1.css">
</head>
<body>
  <div id="qunit"></div>
  <div id="qunit-fixture"></div>
  <script src="https://code.jquery.com/qunit/qunit-2.1.1.js"></script>
  <script src="tests.js"></script>
</body>
</html>
```
The ```qunit-fixture``` element is a container for some HTML that your tests can assert against.  
After each test, QUnit will reset it back to what it was before the test started, so that the next test can run without having to worry about what the previous test added or removed.

**The contents of test/tests.js:**

```javascript
QUnit.test( "a basic test example", function (assert) {
  var value = "hello";
  assert.equal( value, "hello", "We expect value to be hello" );
});
```

**The result (you can see your test in the browser):**

![Test result](pictures/qunit-result.png)

Let’s write some tests to solve [FizzBuzz problem](https://github.com/skibinska/fizzbuzz)!

