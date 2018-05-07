---
Null/nil references
---
* Which does the language support?
 *  A: It supports null references.
* Does this language have any features handling null/nil?
 *  A: The value null is written with a literal: null, null is not an identifier fo a property of global object,instead, null express a lack of identification, indicating variable opints to no oibject.
* An example:
 

``` 
  function getVowels(str) {
  var m = str.match(‘hi’);
  if (m === null) {
    return 0;
   }
  return m.length;
 }
console.log(getVowels('sky')); output: 0
```
