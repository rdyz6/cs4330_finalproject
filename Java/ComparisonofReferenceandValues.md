# Comparision of Reference and Value
## Passing by value
Passing by value constitutes copying of data, where changes to the copied value are not reflected in the original value
For example, if we call a method that accepts a single integer argument and the method makes an assignment to this argument, 
the assignment is not preserved once the method returns. While one might expect that the assignment is preserved after the method returns, the assignment is lost because the value placed on the call stack was a copy of the value passed into the method, as illustrated in the snippet below:
```Java
public void tricky(Point arg1, Point arg2)
{
  arg1.x = 100;
  arg1.y = 100;
  Point temp = arg1;
  arg1 = arg2;
  arg2 = temp;
}
public static void main(String [] args)
{
  Point pnt1 = new Point(0,0);
  Point pnt2 = new Point(0,0);
  System.out.println("X: " + pnt1.x + " Y: " +pnt1.y); 
  System.out.println("X: " + pnt2.x + " Y: " +pnt2.y);
  System.out.println(" ");
  tricky(pnt1,pnt2);
  System.out.println("X: " + pnt1.x + " Y:" + pnt1.y); 
  System.out.println("X: " + pnt2.x + " Y: " +pnt2.y);  
}
```
Output:
- X: 0 Y: 0
- X: 0 Y: 0
- X: 100 Y: 100
- X: 0 Y: 0

We see that the change made to the argument passed into the process function was not preserved after we exited the scope of the function. This loss of data was due to the fact that a copy of the value held by the someValue variable was placed on the call stack prior to the execution of the process function.
Additionally, the action of popping the call stack at the completion of the process method is illustrated in the figure below. Note that the value copied as the argument to the process method is lost (reclaimed) once the call stack is popped, and therefore, 
all changes made to that value are in turn lost during the reclamation step.
## Passing by Reference
Passing by reference consitutes the aliasing of data, where changes to the aliased value are reflected in the original value
Unlike passing by value, passing by reference ensures that a change made to a value in a different scope is preserved when that scope is exited. For example, if we pass a single argument into a method by reference, and the method makes an assignment to that value within its body, the assignment is preserved when the method exits. 
