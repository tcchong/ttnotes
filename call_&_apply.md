# Call & Apply

> Both call() & apply() methods calls a function with a given `this` value, call() accpet an argument list, apply() acceps a single array of arguments

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
- https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/call
- https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/apply
- http://javascriptissexy.com/javascript-apply-call-and-bind-methods-are-essential-for-javascript-professionals/