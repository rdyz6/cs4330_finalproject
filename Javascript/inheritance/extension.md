---
Inheritance/extension
---
* When it comes to inheritance, javascript only has one construct: object. 
* Each pbject has a private proety which holds the link to another object called prototype. Unril an object reaches with null as its prototype, which does not have the prototype, and thus represents the end of the prototype chain. When trying to access a property of an object, the property will not only be sought on the object but on the prototype of the object, the prototype of the prototype, and so on until either a property with a matching name is found or the end of the prototype chain is reached.

* The following example will supports that the property is in fact relate to the prototype of the project.

```
let f = function () {
   this.a = 1;
   this.b = 2;
}
let o = new f(); // {a: 1, b: 2}

//add properties in f function's prototype
 f.prototype.b = 3;
 f.prototype.c = 4;
console.log(o.a); //output1
console.log(o.b); //output2
console.log(o.c); //undefined
console.log(o.d); //undefined


Inheriting methods:
JavaScript does not have “methods” in the form that class based-language defines
 them, In javascript, any function can be added to an object in the form of a 
 property.
var o = {
  a: 2,
  m: function() {
    return this.a + 1;
  }
};

console.log(o.m()); // 3

var p = Object.create(o);
p.a = 4; // creates a property 'a' on p
console.log(p.m()); // 5
```



    
