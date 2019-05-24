# Understanding Closures

#### What is closure?

Closure is when an inner function has access to the outer function's variables. It maintains access to all variables in the outer function even after the function has returned.

##### It has access to the variables in:
1) its own scope
2) its parent function's scope
3) the global scope

##### How does it work?

When you are returning an inner function from a function,

1) You must save the invocation of the outer function to a variable
2) Call/invoke the variable you saved the function to in order to execute the inner function

###### Examples:


1) What does `multiplyByTwo(5);` return?

```js
function multiply (x) {
  return function(y) {
    return x * y;
  }
}

var multiplyByTwo = multiply(10);
multiplyByTwo(5); //50
```

2) What does `sayMyName('Mary')` return?
What does `yellMyName()` return?

```js
function sayMyName (name) {
  return function() {
    return `My name is ${name}`;
  }
}

sayMyName('Mary');

var yellMyName = sayMyName('Joe');
yellMyName();
```
