# Scope Problems

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