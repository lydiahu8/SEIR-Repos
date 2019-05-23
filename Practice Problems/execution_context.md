# Understanding Execution Context

#### What is execution context?

Execution context is the environment that a function is executed in. The call stack is a collection of execution contexts.

##### 2 main types of `Execution Context` in Javascript:

1) **Global Execution Context:**

    - Default or base execution context when a file first loads in browser
    - There can only be one global context because there is only one global environment for JS code to execute
    - Any code outside of a function is in the global execution context

2) **Functional Execution Context:**

    - The context created by the execution of code inside a function
    - Each function has its own execution context, but is only created when the function is called or invoked
    - Each time the function is invoked, a new execution context is created and added to the execution context stack

###### Examples:

1) What does `countNum(10)` return?

```js
var num1 = 10;

function addNums (num2) {
  return num1 + num2;
}

function countNum (num) {
  return addNums(num) + addNums(num);
}

countNum(10); //40
```
