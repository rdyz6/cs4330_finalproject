## packages and the Java Namespaces
A package is a named collection of classes (and possibly subpackages). Packages serve to group related classes and define a namespace for the classes they contain.
## Defining a package
To specify the package a class is to be part of, you use a package directive. The package keyword, if it appears, must be the first token of Java code (i.e., the first thing other than comments and space) in the Java file. The keyword should be followed by the name of the desired package and a semicolon. Consider a file of Java code that begins with this directive:
```Java
package com.davidflanagan.jude;	
```
## Importing Classes and Packages
The import directive is available in two forms. To specify a single class that can be referred to by its simple name, follow the import keyword with the name of the class and a semicolon:
```Java
import java.io.File;    // Now we can type File instead of java.io.File
```
To import an entire package of classes, follow import with the name of the package, the characters .*, and a semicolon. Thus, if you want to use several other classes from the java.io package in addition to the File class, you can simply import the entire package:
```Java
import java.io.*;   // Now we can use simple names for all classes in java.io
```
## Globally Unique Package Names
One of the important functions of packages is to partition the Java namespace and prevent name collisions between classes. It is only their package names that keep the java.util.List and java.awt.List classes distinct, for example. In order for this to work, however, package names must themselves be distinct. As the developer of Java, Sun controls all package names that begin with java, javax, and sun.
