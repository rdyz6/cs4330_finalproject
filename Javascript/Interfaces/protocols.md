---
Interfaces / protocols
---
* What does the language support?

 *  A: JavaScript is a prototype-based language, meaning that object properties and methods can be shared through generalized objects that have the ability to be clone and extended, which is known as prototypical inheritance. It supports both mutable and immutable prototypes, whereas classical inheritance only supports immutable classes. It also inherit mutiple prototypes, java only inherits one 
classes. 
	

* What abilities does it have?
 *  A: In prototype language we only have objects instead of classes,2) Functional features can be used inconjunction with create.3) Prototypal inheritance is simple and easy to understand.

* How is it used?
* It is used like the following 

```	
     function Rectangle(width, height) {
	 2     this.height = height;
	 3     this.width = width;
	 4 }
	 5 
	 6 Rectangle.prototype.area = function () {
	 7     return this.width * this.height;
	 8 };
 
	10 var rect = new Rectangle(5, 10);
    console.log(rect.area());
   Output: 50
```	

