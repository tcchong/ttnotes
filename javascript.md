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

### Call & Applu

> Both call\(\) & apply\(\) methods calls a function with a given `this` value, call\(\) accpet an argument list, apply\(\) acceps a single array of arguments

### Borrow method

```js
// Borrow method from Array.prototype
function transform() {
    var prefix = arguments[0];
    var args = Array.prototype.slice.call(arguments, 1);
    return args.toString().replace(/,/g, prefix);
}

console.log(transform('.', 'first', 'second', 'third'));
// first.second.third
```

## References

* [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Function/call](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/call)
* [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Function/apply](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/apply)
* [http://javascriptissexy.com/javascript-apply-call-and-bind-methods-are-essential-for-javascript-professionals/](http://javascriptissexy.com/javascript-apply-call-and-bind-methods-are-essential-for-javascript-professionals/)



