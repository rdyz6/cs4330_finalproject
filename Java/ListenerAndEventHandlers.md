# Listener and Event Handler
## Event listeners
Event listeners represent the interfaces responsible to handle events. Java provides various Event listener classes, however, only those which are more frequently used will be discussed. Every method of an event listener method has a single argument as an object which is the subclass of EventObject class. For example, mouse event listener methods will accept instance of MouseEvent, where MouseEvent derives from EventObject.
Example:
```Java
public class Beeper ... implements ActionListener {
    ...
    //where initialization occurs:
        button.addActionListener(this);
    ...
    public void actionPerformed(ActionEvent e) {
        ...//Make a beep sound...
    }
}
```
The Beeper class implements the ActionListener interface, which contains one method: actionPerformed. Since Beeper implements ActionListener, a Beeper object can register as a listener for the action events that buttons fire. Once the Beeper has been registered using the Button addActionListener method, the Beeper's actionPerformed method is called every time the button is clicked.
