---
Comparisons of references and values
---
  
* Javascript has both strict and ty[e-converting comparison. A strict comparison (===) is only true if operands contains the same type
  and the content match, the abstract type comparison(==) is not very strict, and is more commonly used.
The following are examples of what I described above:

```
console.log(1 == 1);
output: true

console.log("1" == 1);
output: true

console.log(1 === 1);
output: true
console.log("1" === 1);
output: false 
```
* String comparsion:
C language programmer prefer using strcmp function for comparing strings. In javascript, we just need to use the less-than and greater-than operator:

```
var a = 'a';
var b = 'b';
if (a < b) {
  console.log(a + ' is less than ' + b);
} 
else if (a > b) {
  console.log(a + ' is greater than ' + b);
} else {
  console.log(a + ' and ' + b + ' are equal.');
} 
output: a is less than b
```
* The second approach is using the localecompare() method inherited by String instance
  *  The localeCompare method returns a number indicating whether str1 comes before, after or is the same as str2 in sort order.
