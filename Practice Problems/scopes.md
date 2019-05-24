# Understanding Javascript Scopes

## Global Scope

##### What is global scope?

Variables defined outside of a function is in the global scope. You start out in your global scope every time you start to write code in a Javascript document.

###### Examples: 

1) What does `getApples(50)` return?

```js
var apples = 100;

function getApples () {
  return apples;
}

getApples(50); // 100
```

2) What does `getApples(50)` return?

```js
var apples = 100;

function getApples (apples) {
  return apples;
}

getApples(50); // 50
```

## Local Scope

##### What is local scope?

Variables defined inside of a function is in the local scope. You can use the same variable name within different functions because each variable is bound to its own respective function. This means those variables are not accessible in other functions. Each function invocation creates a new local scope.

###### Examples: 

1) What does `getName('Joe')` return?

```js
var name = 'Sam';

function getName () {
  return name;
}

function reassign (newName) {
  var name = newName;
}

reassign('May');
getName('Joe'); // 'Sam'
```

2) What does `getName('Joe')` return?

```js
var name = 'Sam';

function getName () {
  return name;
}

function reassign (newName) {
  name = newName;
}

reassign('May');
getName('Joe'); // 'May'
```

3) What does `getName('Joe')` return?

```js
var name = 'Sam';

function getName (name) {
  return name;
}

function reassign (newName) {
  name = newName;
}

reassign('May');
getName('Joe'); // 'Joe'
```

## Lexical Scope

##### What is lexical scope?

Lexical scope is when the inner functions of a group of nested functions has access to the variables in their parent scope even if the parent function has returned. However, the parent functions do not have access to the inner function's variables. It only works one way.

A variable with the same name in the innermost function of a nested group of functions will take precedence over the variable in the parent functions.

###### Examples:

1) What does `reassignNum()` return?
```js
function reassignNum () {
  var num = 100;

  function reassignOnce () {
    num = 60;
    function reassignTwice () {
      num = num * 2;
    }
    reassignTwice();
  }
  reassignOnce();
  return num;
}

reassignNum(); // 120
```

2) What does `reassignNum()` return?

```js
function reassignNum () {
  var num = 100;

  function reassignOnce () {
    var num = 60;
    function reassignTwice () {
      num = num * 2;
    }
    reassignTwice();
  }
  reassignOnce();
  return num;
}

reassignNum(); // 100
```

3) What does `reassignNum()` return?

```js
function reassignNum () {
  var num = 100;

  function reassignOnce () {
    num = 60;
    function reassignTwice () {
      var num = num * 2;
    }
    reassignTwice();
  }
  reassignOnce();
  return num;
}

reassignNum(); // 60
```

