# Learn QUnit

A quick introduction to JavaScript unit testing with QUnit.js.

## What is testing?  

Testing is a process of executing a program or application with the intent of finding the **bugs**.  
It can also be stated as the process of **validating** and **verifying** that a software program or application:  
- Meets the business and technical requirements that guided it’s design and development
- Works as expected
- Can be implemented with the same characteristic.

## Why is testing necessary?

Testing is necessary because we all make mistakes. Some of those mistakes are unimportant, but some of them are expensive or dangerous. We need to check everything and anything we produce because things can always go wrong.

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

The contents of qunit.html:

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
The contents of tests.js:

```javascript
QUnit.test( "a basic test example", function (assert) {
  var value = "hello";
  assert.equal( value, "hello", "We expect value to be hello" );
});
```

The result:

![Test result](pictures/qunit-result.png)



