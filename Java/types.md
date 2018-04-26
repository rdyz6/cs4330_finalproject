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

