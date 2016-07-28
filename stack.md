## Stack in JS

```js
// Linked List stack
function Stack() {
    this.top = null;
    this.size = 0;
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
    this.size -= 1;
    return lastTop;
}

Stack.prototype.push = function(value) {
    var node = new Node(value);
    node.previous = this.top;
    this.top = node;
    this.size += 1;
    return this.top;
}

var s = new Stack();
s.push(1); // Node {data: 1, previous: null}
s.push(2); // Node {data: 2, previous: Node}
s.push(3); // Node {data: 3, previous: Node}
s.peek(); // Node {data: 3, previous: Node}
s.pop(); // Node {data: 3, previous: Node}
s.peek(); // Node {data: 2, previous: Node}
```