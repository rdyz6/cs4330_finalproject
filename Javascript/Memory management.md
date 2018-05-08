---
Memory management 
---
* How is it handled?
 *  A: javascript, unlike lower level language uses malloc() and free() to manage the memory,allocates strings when things are created and automatically freed when they are not used anymore.
* How does it works?
 *  A: It has a lifecycle with three stages: Allocation: including value initialization, function calls. Using the allocated memory, and release the allocated memory when it is not needed anymore
* Garbage collection?
 *  A: The main notion of the garbage collections algorithm really relys on the notion of reference. An object is said to reference other object if the former has an access to the latter one.Example:

```
var o = { 
  a: {
    b: 2
  }
}; 
var o2 = o; 
o = 1;      
var oa = o2.a; 
o2 = 'yo';         
oa = null; 
```

* Automatic reference counting:
*  A: Automatic reference counting(ARC) is a garbage collection technique with a simple algorithm: every object stores a special values which is increased everytime a new reference is assigned the address of this object. In javascript, to manage reference counting special value,
we use “allocate” function which Initialize reference counting flag top zero, and also provides actual allocation of this project on the heap.

```
Function allocate(obj) { 
var allocateaddress = heap.length; 
obj._rc_ = 0; 
heap.push(obj); 
return allocAddress; 
}
``` 
