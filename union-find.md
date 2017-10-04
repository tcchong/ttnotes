# Union Find

> Implement example from [algorithms course](https://www.coursera.org/learn/algorithms-part1) with JS

### Quick Find

union: N

find: 1

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

### Quick Union

```js
class QuickUnion {
  constructor(length) {
    this.list = [];
    for (let i = 0;i < length; i++) {
        this.list[i] = i;
    }
  }

  _root(index) {
      // Get the root of tree
      while (index !== this.list[index]) {
        index = this.list[index];
    }
    return index;
  }

  union(p, q) {
    this.list[this._root(p)] = this._root(q);
  }

  connected(p, q) {
    return this._root(p) === this._root(q);
  }
}

const qu = new QuickUnion(10);

qu.union(4, 3); // [0, 1, 2, 3, 3, 5, 6, 7, 8, 9]
qu.union(3, 8); // [0, 1, 2, 8, 3, 5, 6, 7, 8, 9]
qu.union(6, 5); // [0, 1, 2, 8, 3, 5, 5, 7, 8, 9]
qu.union(9, 4); // [0, 1, 2, 8, 3, 5, 5, 7, 8, 8]
console.log(qu.connected(8, 9)); // true
console.log(qu.connected(5, 4)); // false
qu.union(2, 1); // [0, 1, 1, 8, 3, 5, 5, 7, 8, 8]
qu.union(5, 0); // [0, 1, 1, 8, 3, 0, 5, 7, 8, 8]
qu.union(7, 2); // [0, 1, 1, 8, 3, 0, 5, 1, 8, 8]
qu.union(6, 1); // [1, 1, 1, 8, 3, 0, 5, 1, 8, 8]
qu.union(7, 3); // [1, 8, 1, 8, 3, 0, 5, 1, 8, 8]
```

### Weighted Quick Union

```js
class WeightedQuickUnion {
  constructor(length) {
    this.list = [];
    this.size = [];
    for (let i = 0; i < length; i++) {
      this.list[i] = i;
      this.size[i] = 1;
    }
  }

  _root(index) {
    // Get the root of tree
    while (index !== this.list[index]) {
      index = this.list[index];
    }
    return index;
  }

  union(p, q) {
    const { size, list } = this;
    const rootP = this._root(p);
    const rootQ = this._root(q);

    if (rootP === rootQ) {
      return;
    }

    if (size[rootP] < size[rootQ]) {
      list[rootP] = rootQ;
      size[rootQ] += size[rootP];
    } else {
      list[rootQ] = rootP;
      size[rootP] += size[rootQ];
    }
  }

  connected(p, q) {
    return this._root(p) === this._root(q);
  }
}

const wqu = new WeightedQuickUnion(10);

wqu.union(4, 3); // [0, 1, 2, 4, 4, 5, 6, 7, 8, 9]
wqu.union(3, 8); // [0, 1, 2, 4, 4, 5, 6, 7, 4, 9]
wqu.union(6, 5); // [0, 1, 2, 4, 4, 6, 6, 7, 4, 9]
wqu.union(6, 8); // [0, 1, 2, 4, 4, 6, 4, 7, 4, 9]
wqu.connected(4, 5); // true
```

### 

### Reference

[https://www.coursera.org/learn/algorithms-part1](https://www.coursera.org/learn/algorithms-part1)

