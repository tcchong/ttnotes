# JavaScript

## Closure

> A closure is an inner function that has access to the variables in the outer enclosing function scope chain

```
function outer() {
  var outerVal = 'value';

  function inner() {
    console.log(outerVal); // value
  }
}
```

## Hoisting

```
// function declarations
fd(); // YA!!!

function fd() {
  console.log('YA!!!');
}

// function expressions
fe(); // TypeError: .....

var fe = function() {
  console.log('NO!!!');
};
```

## Scope

> Javascript does not support block level scoping

```js
if (true) {
  var test = 'value';
}

console.log(test); // value
```

> Support block level scopes via the let keyword

```js
if (true) {
  let test = 'value';
}
console.log(test); // SyntaxError: ......
```

