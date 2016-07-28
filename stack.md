## Stack in JS

```js
// Linked List stack
function Stack() {
    this.top = null;this.size = 0;
}
function Node(data) {
    this.data = data;
    this.previous = null;
}

Stack.prototype.peek = function() {
    return this.top;
}

Stack.prototype.pop = function() {
    var lastTop = this.top;
    this.top = lastTop.previous;
    this.size -= 1;return lastTop;
}

Stack.prototype.push = function(value) {
    var node = new Node(value);
    node.previous = this.top;
    this.top = node;
    this.size += 1;
    return this.top;
}
```