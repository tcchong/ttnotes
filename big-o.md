# Overview

* Describe how closely a finite series approximates a given function
* Analyzing algorithms for efficiency in computer science

f\(n\) = O\(g\(x\)\)  
f\(n\) &lt;= c \* \(g\(n\)\)

| Notation | Name |
| --- | --- |
| O\(1\) | constant |
| O\(N\) | linear |
| O\(N^2\) | quadratic |

```js
// O(1)
function getFirstIndex(list) {
  return list[0];
}

// O(n)
function iterator(list) {
  for (var i = 0; i < list.length; i++) {
    // do something
  } 
}

// O(n^2)
function iterator(list) {
 for (var i = 0; i < list.length; i++) {
   for (var j = 0; j < list2.length; j++) {
     // do something
   }
 }
}
```

# Reference

[https://en.wikipedia.org/wiki/Big\_O\_notation](https://en.wikipedia.org/wiki/Big_O_notation)

