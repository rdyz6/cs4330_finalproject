---
NameSpace
---
* Global variables should be reserved for objects that have system-wide relevance and they should be named to avoid ambiguity and minmiz the risk of naming collision, which means we should aboid creating global variables unless it’s necessary. 
* The best global abatement strategy is to create a small number of global objects which will serve as the facto namespaces for underlying modules and subsystems.
* Here are the implementation:
** Direct assignment:

```
var myApp = {}
myApp.id = 0;
myApp.next = function() {
    return myApp.id++;  
}
myApp.reset = function() {
    myApp.id = 0;   
}
window.console && console.log(
    myApp.next(),
    myApp.next(),
    myApp.reset(),
    myApp.next()
); //0, 1, undefined, 0 

**Using the object literal notation:
var myApp = {
    id: 0,
next: function() {
    return this.id++;   
},
reset: function() {
        this.id = 0;    
    }
}
window.console && console.log(
    myApp.next(),
    myApp.next(),
    myApp.reset(),
myApp.next()) //0, 1, undefined, 0

The module pattern: 
var myApp = (function() {
var id= 0;
return {
   next: function() {
     return id++;    
   },
reset: function() {
     id = 0;     
        }
    };  
})();   
window.console && console.log(
    myApp.next(),
    myApp.next(),
    myApp.reset(),
    myApp.next()
) //0, 1, undefined, 0  
```

* The concept of namespaces, whereas exists in other programming languagedoes not exist in JavaScript. To add insult to injury, everything you create in JavaScript is by default global. To solve this problem we can create a single global object for your app and make all functions and variables properties of that global object.


