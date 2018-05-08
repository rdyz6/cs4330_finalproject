---
Procedural and functional programming
---
* Javascript does support both prodedural and functional programming
 *  Procedural Programming, which is based on concepts of procedure-call-like routines and subroutines.
 *  Functional Programming, which is based on expressions like variables, constants, functions and operators.
 
 * In javascript:
  *  Procedural programming typically involves your code executing at the top of your script and going in order, statement by statement, to the
 bottom. 
  *  Functional programming, however, centers more around the idea of the programming describing what should be done to an input and le
 -ss around the order in which that should occur.
 
 * Procedural programming:
 
 ```
 function getValue(object, propertyname){
     var object1 = object, part, i;
     if(typeof propertyname !== 'string' || propertyname === null){
        throw new Error("invalid input, try it again please");
     }
     part = propertyname.split('.');
     for(i = 0; i<=propertyname.length; i++){
      if(typeof object1 === 'undefined'){
          return undefined
      }
      object1 = onject1[part[i]];
     }
     return object1;
 }(pretty complicated and cumbersome)
 ```
 * Functional programming:
 
 ```
 function getsimpleValue(object, propertyname){
    if(typeof propertyname !== 'string' || propertyname === null){
        throw new Error("invalid input, try it again please");
     }
     return typeof object === 'undefined'? undefined: object[propertyname]
   }
 function getcomplicateValue(object, propertyname){
     return propertyname.split('.').reduce(getsimplevalue, object);
   }(A lot easier)
```
