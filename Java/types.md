# type
## boolean
boolean data type represents only one bit of information either true or false . 
Values of type boolean are not converted implicitly or explicitly (with casts) to any other type. 
But the programmer can easily write conversion code.
```
class theclass{
    public static void main(String args[]){
        boolean b = true;
    }
}
```
## byte
The byte data type is an 8-bit signed two’s complement integer.The byte data type is useful for saving memory in large arrays.
- size: 8 bit
- value: -128 ~ 127
```
class theclass
{
    public static void main(String args[]) 
    {
        byte a = 126;
        System.out.println(a);
        a++;
        System.out.println(a);
        a++;
        System.out.println(a);
        a++;
        System.out.println(a);
    }    
}
```
output:
- 126
- 127
- -128
- -127
## short
The short data type is a 16-bit signed two’s complement integer. Similar to byte, use a short to save memory in large arrays, in situations where the memory savings actually matters.
- size: 16bit
- value: -2^31 to 2^31-1\
##long
The long data type is a 64-bit two’s complement integer.
- size: 64 bit
- value: -2^63 to 2^63-1.
Note: In Java SE 8 and later, you can use the long data type to represent an unsigned 64-bit long, which has a minimum value of 0 and a maximum value of 264-1. The Long class also contains methods like compareUnsigned, divideUnsigned etc to support arithmetic operations for unsigned long.
## float
The float data type is a single-precision 32-bit IEEE 754 floating point. Use a float (instead of double) if you need to save memory in large arrays of floating point numbers.
- size: 32 bits
- suffix : F/f Example: 9.8f
## double
The double data type is a double-precision 64-bit IEEE 754 floating point. For decimal values, this data type is generally the default choice.

Note: Both float and double data types were designed especially for scientific calculations, where approximation errors are acceptable. If accuracy is the most prior concern then, it is recommended not to use these data types and use BigDecimal class instead.
Please see this for details: Rounding off errors in Java
## char
The char data type is a single 16-bit Unicode character. A char is a single character.
- value: ‘\u0000’ (or 0) to ‘\uffff’ 65535
```
class theclass
{
    public static void main(String args[]) 
    {
         char a = 'A';
         int i=1;
         byte b = 2;
         short s = 3;
         double d = 4.355453532;
         float f = 4.7333434f;
        
        System.out.println("char: " + a); 
        System.out.println("integer: " + i); 
        System.out.println("byte: " + b); 
        System.out.println("short: " + s); 
        System.out.println("double: " + d); 
        System.out.println("float: " + f); 
        
    }    
}
```
output:
- char: A
- integer: 1
- byte: 2
- short: 3
- double: 4.355453532
- float: 4.7333434f
