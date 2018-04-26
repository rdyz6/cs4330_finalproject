# Null Reference
In Java programming, null can be assigned to any variable of a reference type (that is, a non-primitive type) to indicate that the variable does not refer to any object or array. CORBA also allows null object references, but it is important to note that not all Java reference types map to CORBA object references. Therefore, you might encounter situations where a null object reference that would be appropriate in a non-distributed Java program is not appropriate in a distributed Java program using CORBA. If null is used improperly in a method call on a Java CORBA stub, the method will throw a java.lang.NullPointerException.
When calling methods on Java CORBA stubs like the IOM object stubs, null might only be used in place of a reference to any Java object that implements org.omg.CORBA.Object. That means that null cannot be used in place of a reference to a Java object like an instance of java.lang.String or a Java array.
The GetApplication method on the Java CORBA IOM stub com.sas.iom.SAS.IWorkspace provides a good example. Here is the method signature for this method.
```Java
     public org.omg.CORBA.Object GetApplication
     (
          java.lang.String application
     )
     throws
          com.sas.iom.SASIOMDefs.GenericError
```
When calling this method, the value of the parameter application cannot be null because its type, java.lang.String, does not implement org.omg.CORBA.Object. However, the return value of the method can be null because the returned value does implement org.omg.CORBA.Object.

