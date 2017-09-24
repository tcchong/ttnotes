# Quick Find



```js
// https://jsfiddle.net/7npz10hx/3/
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

const qf = new QuickFind(10);
```



