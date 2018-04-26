# Reflection
## What is reflection
Reflection is a feature in the Java programming language. It allows an executing Java program to examine or "introspect" upon itself, and manipulate internal properties of the program. For example, it's possible for a Java class to obtain the names of all its members and display them.
The ability to examine and manipulate a Java class from within itself may not sound like very much, but in other programming languages this feature simply doesn't exist. For example, there is no way in a Pascal, C, or C++ program to obtain information about the functions defined within that program.
One tangible use of reflection is in JavaBeans, where software components can be manipulated visually via a builder tool. The tool uses reflection to obtain the properties of Java components (classes) as they are dynamically loaded.

```Java
import java.lang.reflect.*;
 
   public class DumpMethods {
      public static void main(String args[])
      {
         try {
            Class c = Class.forName(args[0]);
            Method m[] = c.getDeclaredMethods();
            for (int i = 0; i < m.length; i++)
            System.out.println(m[i].toString());
         }
         catch (Throwable e) {
            System.err.println(e);
         }
      }
   }
```
## set reflection
The reflection classes, such as Method, are found in java.lang.reflect. There are three steps that must be followed to use these classes. The first step is to obtain a java.lang.Class object for the class that you want to manipulate. java.lang.Class is used to represent classes and interfaces in a running Java program.
One way of obtaining a Class object is to say:
```Java
   Class c = Class.forName("java.lang.String");
```
to get the Class object for String. Another approach is to use:
```Java   
   Class c = int.class;
```
or
```Java
  Class c = Integer.TYPE;
```
to obtain Class information on fundamental types. The latter approach accesses the predefined TYPE field of the wrapper (such as Integer) for the fundamental type.
The second step is to call a method such as getDeclaredMethods, to get a list of all the methods declared by the class.

