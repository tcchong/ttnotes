# Call & Apply


### Borrow method

```js
function transform() {
    var prefix = arguments[0];
    var args = Array.prototype.slice.call(arguments, 1);
    return args.toString().replace(/,/g, prefix);
}

console.log(transform('.', 'first', 'second', 'third'));
// first.second.third
```