# Revealing module

```
var myLib = (function() {

  function privateMethod() {
    console.log('private');
  };

  function publicMethod() {
    console.log('public');
  };
  
  return {
    doSomething: publicMethod
  }

})();

myLib.doSomething(); // public
myLib.privateMethod(); // Uncaught TypeError: myLib.privateMethod is not a function
```

