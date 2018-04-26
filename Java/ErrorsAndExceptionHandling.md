# Error and Exception
- Recovering from Error is not possible. The only solution to errors is to terminate the execution. Where as you can recover from Exception by using either try-catch blocks or throwing exception back to caller.
- You will not be able to handle the Errors using try-catch blocks. Even if you handle them using try-catch blocks, your application will not recover if they happen. On the other hand, Exceptions can be handled using try-catch blocks and can make program flow normal if they happen.
- Exceptions in java are divided into two categories – checked and unchecked. Where as all Errors belongs to only one category i.e unchecked.
- Compiler will not have any knowledge about unchecked exceptions which include Errors and sub classes of RunTimeException because they happen at run time. Where as compiler will have knowledge about checked Exceptions. Compiler will force you to keep try-catch blocks if it sees any statements which may throw checked exceptions.
- Exceptions are related to application where as Errors are related to environment in which application is running.
Exception Example:
```Java
import java.io.File;
import java.io.FileReader;

public class FilenotFound_Demo {

   public static void main(String args[]) {		
      File file = new File("E://file.txt");
      FileReader fr = new FileReader(file); 
   }
}
```
output:
```Java
C:\>javac FilenotFound_Demo.java
FilenotFound_Demo.java:8: error: unreported exception FileNotFoundException; must be caught or declared to be thrown
      FileReader fr = new FileReader(file);
                      ^
1 error
```
