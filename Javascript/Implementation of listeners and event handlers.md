---
Listner and events handler
---

* Events are actions or occurrences that happen in the system you are programming, which the system tells you about so you can respond to 
them in some way if desired. For example, if the user clicks a button on a webpage

* To add the listener, we implements like this, 

```
element.addEventListener(event, function, userCapture),
var btn = document.querySelector('button');
function Change() {
  var rndCol = 'rgb(' + random(255) + ',' + random(255) + ',' + random(255) + ')';
  document.body.style.backgroundColor = rndCol;
}   

btn.addEventListener('click', Change);
```


* Where the first elements is the type of the event, the second element is the function want to call when the events occurs, the third elements is the boolean value whether the events is bubbling or captured. To remove the listener, we just need to do 

```
document.removeEventListener(“mousemove”, the name of the function).
```
* If event handler refers to a specific element on the page, and calling script before the element loads, the script won't work because the element isn't available at the time the script runs. THe solution for this problem is to insert a script before the closing body
tag. 
* Here, we can use the preparehandlerfunction()

```
//declare the function
function preparehandlerfunction() {
//get a specific page ID and assign it as a variable
var specialSection = document.getElementById("specialSection");
//initiate this function when the ID is clicked
specialSection.onclick = function() {
alert("Hello World");
}
}
window.onload = function() {
prepareEventHandlers();
}
```
