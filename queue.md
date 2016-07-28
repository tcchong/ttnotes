## Queue in JS

```js
function Queue() {
    this.first = null;
    this.last = null;
    this.size = 0;
}

function Node(data) {
    this.data = data;
    this.next = null;
}

Queue.prototype.enqueue = function(value) {
    var node = new Node(value);
    if (this.size === 0) {
        this.first = node;
    } else {
        this.last.next = node;
    }
    this.last = node;
    this.size += 1;
    return this.last;
}

Queue.prototype.dequeue = function() {
    var tmp = this.first;
    this.first = tmp.next;
    return tmp;
}

Queue.prototype.peek = function() {
    return this.first;
}
```