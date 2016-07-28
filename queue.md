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

var q = new Queue();
q.enqueue(1); // Node {data: 1, next: null}
q.enqueue(2); // Node {data: 2, next: null}
q.enqueue(3); // Node {data: 3, next: null}
q.peek(); // Node {data: 1, next: Node}
Objectq.dequeue(); // Node {data: 1, next: Node}
q.peek(); // Node {data: 2, next: Node}
```