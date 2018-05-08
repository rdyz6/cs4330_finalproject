---
TYPE
---
* What types does the language support?
 *  A: It supports primitive types and reference types. Numbers, boolean values, and the null and undefined types are primitive.

* Are both reference and values supported?
 *  A: Yes, 
* Pass by Value:
 *  In Pass by Value, Function is called by directly passing the value of the variable as the argument. Changing the argument inside the function doesn’t affect the variable passed from outside the function.

```
function callbyValue(var1, var2) { 
  console.log("Inside Call by Value Method"); 
  varOne = 100; 
  varTwo = 200; 
  console.log("varOne =" + varOne +"varTwo =" +varTwo); 
} 
let varOne = 10; 
let varTwo = 20; 
console.log("Before Call by Value Method"); 
console.log("varOne =" + varOne +"varTwo =" +varTwo); 
callByValue(varOne, varTwo) 
console.log("After Call by Value Method");
```
* The output will look like following: 100, 200, 10,20, 100, 200(so, the value actually did not change)
* Pass by reference
 *  In Passing by reference, function is called by directly passing the reference/ address of the variable as the argument. Change the argument inside the fucntion affect the variable passed from outside of the function

```
function callByReference(varObj) { 
  console.log("Inside Call by Reference Method"); 
  varObj.a = 100; 
  console.log(varObj); 
} 
let varObj = {a:1};
console.log("Before Call by Reference Method"); 
console.log(varObj);
callByReference(varObj) 
console.log("After Call by Reference Method"); 
console.log(varObj);
output will be : a:1, a:100, a:100
``` 
* Can new value types be created?
 *  A: In my opinion it can. JavaScript is a loosely typed or a dynamic language. Variables in JavaScript are not directly associated with any particular value type, and any variable can be assigned (and re-assigned) values of all types:

