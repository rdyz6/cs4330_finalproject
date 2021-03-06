---
Property
---
* The get syntax binds an object property to a function that will be called when that property is looked up.

```
var obj = {
  log: ['a', 'b', 'c'],
  get latest() {
    if (this.log.length == 0) {
      return undefined;
    }
    return this.log[this.log.length - 1];
  }
}

console.log(obj.latest)
Output: ‘c’;
```
* The set syntax binds an object property to a function to be called when there is an attempt to set that property.

```  
  var language = {
  set current(name) {
    this.log.push(name);
  },
  log: []
}

language.current = 'EN';
language.current = 'FA';

console.log(language.log);It will output the Array ["EN", "FA"];
It’s built in
```
* Backing variable:
 *  A backing variable is where data actually stored.
It bascially combines the getter and setter to make your programming more efficient:An Example:

```
"use strict";

let myClass = class myClass {
  constructor(name) {
    this.name = name;
  }

  get name() {
    return this._name;
  }

  set name(name) {
    this._name = name;
  }
}

let myObj = new myClass("John");

console.log(myObj);
```

* Computed property:
 *  In javascript: With computed property names, instead of having to create an object and then add properties to it using bracket notation, what we can do is return a 
new object, and using object literal notation, put brackets around the key. Now, whatever the variable represents is going to be added as a property on the object.

