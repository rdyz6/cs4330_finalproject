---
Class
---
* Classes are also called the “special function, the class has two components, class expressions and class declaration

```
Class declararion:
class Rectangle {
  constructor(height, width) {
    this.height = height;
    this.width = width;
  }
}
Class expression:
var Rectangle = class {
  constructor(height, width) {
    this.height = height;
    this.width = width;
  }
};
console.log(Rectangle.name);
// output: "Rectangle"

// named
var Rectangle = class Rectangle2 {
  constructor(height, width) {
    this.height = height;
    this.width = width;
  }
};
console.log(Rectangle.name);
// output: "Rectangle2"
```
* To create new instance, The new operator creates an instance of a user-defined object type or of one of the built-in object types that has a constructor function.

```
function Car(make, model, year) {
  this.make = make;
  this.model = model;
  this.year = year;
}

var car1 = new Car('Eagle', 'Talon TSi', 1993);

console.log(car1.make);

Output: eagle.
```
* Initializing and constructing
First method:

```
<script type="text/javascript">
function init(){

}
</script>
```
* Second method(using windows.onload):

```
<script type="text/javascript">
    window.onload=function(){ 
   }
</script>
```
* Deinitializing and destructing

```
Class		deinitializing{
     deinit(){   
 }
}
```



* Javascript constructor:

```
function Person(first, last, age, eye) {
    this.firstName = first;
    this.lastName = last;
    this.age = age;
    this.eyeColor = eye;
}
```
