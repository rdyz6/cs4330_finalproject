---
Instance reference name in data type (class)
--- 
* In most, “this” is determined to how how function is called,  It can't be set by assignment during execution,
and it may be different each time the function is called. ES5 introduced the bind method to set the value of a function's this regardless of how it's called, and ES2015 introduced arrow functions which don't provide their own this binding

* An example:

```
var test = {
  prop: 42,
  func: function() {
    return this.prop;
  },
};

console.log(test.func());
Expected output will be 42
```
