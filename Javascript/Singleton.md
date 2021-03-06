---
Singleton
---

* The singleton pattern is a software design pattern that restrict the instantiation of one object. In javascript, the singleton object is implemented as an anonymous function, which is executes immediately by wrapping it in brackets followed by two additional brackets fol
-lowed by two additional brackets. The getinstance method is Singleton’s gatekeeper. Example:

```
var singleton = (function () {
    var instance;
 
    function createInstance() {
        var object = new Object("hi");
        return object;
    }
 
    return {
        getInstance: function () {
            if (!instance) {
                instance = createInstance();
            }
            return instance;
        }
    };
})();
 
function run() {
 
    var instance1 = Singleton.getInstance();
    var instance2 = Singleton.getInstance();
 
    alert("Same instance? " + (instance1 === instance2));  
}
```
* Can it be made thread safe?
 *  A: Because javascript is single-threaded in the context of broswer, it’s relatively safe
* Can javascript be lazily instantiated?
 *  A: In computer programming, lazy initialization is the tactic of delaying the creation of an object, the calculation of a value, or some other expensive process until the first time it is needed.So, Yes, it can,

```       
var ConstructorName = (function()
       {
	       var singletonInstance = null;
	
	     function ConstructorName()
	     {
		     // presumably expensive instantiation/init code
	     }

	      return function ()
	     {
		     if (singletonInstance === null)
		   {
		    	singletonInstance = new ConstructorName();
		   }
		     return singletonInstance;
      	};
     })();
```
