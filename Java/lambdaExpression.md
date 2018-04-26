# Lambda expression
## What is lambda expression
One issue with anonymous classes is that if the implementation of your anonymous class is very simple, 
such as an interface that contains only one method, then the syntax of anonymous classes may seem unwieldy and unclear. 
In these cases, you're usually trying to pass functionality as an argument to another method, such as what action should be taken when someone clicks a button. Lambda expressions enable you to do this, 
to treat functionality as method argument, or code as data.
Functional programming is very often used to implement event listeners. Event listeners in Java are often defined as Java interfaces with a single method. Here is a fictive single method interface example:
```Java
public interface StateChangeListener {

    public void onStateChange(State oldState, State newState);

}
```
This Java interface defines a single method which is called whenever the state changes (in whatever is being observed).

In Java 7 you would have to implement this interface in order to listen for state changes. Imagine you have a class called StateOwner which can register state event listeners. Here is an example:
```Java
public class StateOwner {

    public void addStateListener(StateChangeListener listener) { ... }

}
```
## Lambda Type Interface
Before Java 8 you would have to specify what interface to implement, when making anonymous interface implementations. Here is the anonymous interface implementation example from the beginning of this text:
```Java
stateOwner.addStateListener(new StateChangeListener() {

    public void onStateChange(State oldState, State newState) {
        // do something with the old and new state.
    }
});
```
With lambda expressions the type can often be inferred from the surrounding code. For instance, the interface type of the parameter can be inferred from the method declaration of the addStateListener() method (the single method on the StateChangeListener interface). This is called type inference. The compiler infers the type of a parameter by looking elsewhere for the type - in this case the method definition. Here is the example from the beginning of this text, showing that the StateChangeListener interface is not mentioned in the lambda expression:
```Java
stateOwner.addStateListener(
    (oldState, newState) -> System.out.println("State changed")
);
```
## Lambda Parameters
Since Java lambda expressions are effectively just methods, lambda expressions can take parameters just like methods. The (oldState, newState) part of the lambda expression shown earlier specifies the parameters the lambda expression takes. These parameters have to match the parameters of the method on the single method interface. In this case, these parameters have to match the parameters of the onStateChange() method of the StateChangeListener interface:
```Java
public void onStateChange(State oldState, State newState);
```
As a minimum the number of parameters in the lambda expression and the method must match.
Second, if you have specified any parameter types in the lambda expression, these types must match too. I haven't shown you how to put types on lambda expression parameters yet (it is shown later in this text), but in many cases you don't need them.
##### zero parametersIf the method you are matching your lambda expression against takes no parameters, then you can write your lambda expression like this:
```Java
() -> System.out.println("Zero parameter lambda");
```
##### one parameters
If the method you are matching your Java lambda expression against takes one parameter, you can write the lambda expression like this:
```Java
(param) -> System.out.println("One parameter: " + param);
```
When a lambda expression takes a single parameter, you can also omit the parentheses, like this:
```Java
 param -> System.out.println("One parameter: " + param);
```
##### multiple parameters
If the method you match your Java lambda expression against takes multiple parameters, the parameters need to be listed inside parentheses. Here is how that looks in Java code:
```Java
(p1, p2) -> System.out.println("Multiple parameters: " + p1 + ", " + p2);
```
## Lambda Function Body
The body of a lambda expression, and thus the body of the function / method it represents, is specified to the right of the -> in the lambda declaration: Here is an example:
```Java
(oldState, newState) -> System.out.println("State changed")
```
If your lambda expression needs to consist of multiple lines, you can enclose the lambda function body inside the { } bracket which Java also requires when declaring methods elsewhere. Here is an example:
```Java
(oldState, newState) -> {
    System.out.println("Old state: " + oldState);
    System.out.println("New state: " + newState);
  }
```
