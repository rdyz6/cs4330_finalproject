---
Reflection:
---
* What type of reflection does this language supports?
 1 A: It supports reflect.get, reflect.defineProperty, reflect.deleteProperty, reflect.has, reflect.getOwnProperty
* How is the reflection used?
 1 A: Traditionally, the reflection is used to load modules that list an assembly, and create an instance of it, without the reflection,
this process will probably take very long time.

* Reflect.construct(): The new operator as a function. Equivalent to calling new target(...args).
* Reflect.deleteProperty(): The delete operator as a function. Equivalent to calling delete target[name].
* Reflect.get(): A function that returns the value of properties
