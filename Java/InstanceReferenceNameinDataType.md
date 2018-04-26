# Instance Reference Name In Data Type
## This
Within an instance method or a constructor, this is a reference to the current object — the object whose method or constructor is being called. 
You can refer to any member of the current object from within an instance method or a constructor by using this.

## using this with a field
The most common reason for using the this keyword is because a field is shadowed by a method or constructor parameter.
```
public class Point {
    public int x = 0;
    public int y = 0;
        
    //constructor
    public Point(int x, int y) {
        this.x = x;
        this.y = y;
    }
}
```
## using this with a constructor
From within a constructor, you can also use the this keyword to call another constructor in the same class. 
Doing so is called an explicit constructor invocation. 
Here's another Rectangle class, with a different implementation from the one in the Objects section.
```
public class Rectangle {
    private int x, y;
    private int width, height;
        
    public Rectangle() {
        this(0, 0, 1, 1);
    }
    public Rectangle(int width, int height) {
        this(0, 0, width, height);
    }
    public Rectangle(int x, int y, int width, int height) {
        this.x = x;
        this.y = y;
        this.width = width;
        this.height = height;
    }
    ...
}
```
