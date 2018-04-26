## Interfaces
Java includes a concept called interfaces. 
A Java interface is a bit like a class, except a Java interface can only contain method signatures and fields. An Java interface cannot contain an implementation of the methods, 
only the signature (name, parameters and exceptions) of the method.
```Java
    public interface myinterface{
        public String hello = "Hello";
        public void sayHello();
    }
```
## implement an interface
Before you can really use an interface, you must implement that interface in some Java class. 
Here is a class that implements the MyInterface interface shown above:
```Java
    public class MyInterfaceImpl implements MyInterface {

        public void sayHello() {
            System.out.println(MyInterface.hello);
        }
    }
```
A class that implements an interface must implement all the methods declared in the interface. The methods must have the exact same signature (name + parameters) as declared in the interface. 
The class does not need to implement (declare) the variables of an interface. Only the methods.
## Interface Instances
Once a Java class implements an Java interface you can use an instance of that class as an instance of that interface. 
```Java
    MyInterface myInterface = new MyInterfaceImpl();
    myInterface.sayHello();
```
Notice how the variable is declared to be of the interface type MyInterface while the object created is of type MyInterfaceImpl. Java allows this because the class MyInterfaceImpl implements the MyInterface interface. You can then reference instances of the MyInterfaceImpl class as instances of the MyInterface interface.
You cannot create instances of a Java interface by itself. You must always create an instance of some class that implements the interface, and reference that instance as an instance of the interface.
## Implementing mutiple Interfaces
A Java class can implement multiple Java interfaces. In that case the class must implement all the methods declared in all the interfaces implemented. Here is an example:
```Java
    public class MyInterfaceImpl
        implements MyInterface, MyOtherInterface {
        public void sayHello() {
            System.out.println("Hello");
        }
        public void sayGoodbye() {
            System.out.println("Goodbye");
        }
    } 
```
## Interface Variables
A Java interface can contain both variables and constants. However, often it does not makes sense to place variables in an interface. In some cases it can make sense to define constants in an interface. Especially if those constants are to be used by the classes implementing the interface, e.g. in calculations, or as parameters to some of the methods in the interface. However, my advice to you is to avoid placing variables in Java interfaces if you can.
All variables in an interface are public, even if you leave out the public keyword in the variable declaration.

## Interface Methods
A Java interface can contain one or more method declarations. As mentioned earlier, the interface cannot specify any implementation for these methods. It is up to the classes implementing the interface to specify an implementation.
All methods in an interface are public, even if you leave out the public keyword in the method declaration.

