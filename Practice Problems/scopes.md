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

