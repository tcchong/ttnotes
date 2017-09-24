# Quick Find

```js
class QuickFind {
  constructor(length) {
    this.list = [];
    for (let i = 0;i < length; i++) {
        this.list[i] = i;
    }
  }

  union(p, q) {
    const pVal = this.list[p];
    const qVal = this.list[q];

    this.list.forEach((item, index) => {
        if (item === pVal) {
          this.list[index] = qVal;
      }
    });
  }

  connected(p, q) {
    return this.list[p] === this.list[q];
  }
}

const qf = new QuickFind(10); // [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]

qf.union(1, 2);      // [0, 2, 2, 3, 4, 5, 6, 7, 8, 9]
qf.connected(1, 2);  // true
qf.union(6, 7);      // [0, 2, 2, 3, 4, 5, 7, 7, 8, 9]
qf.union(1, 6);      // [0, 7, 7, 3, 4, 5, 7, 7, 8, 9]
qf.connected(2, 7);  // true
```

union: N

find: 1

