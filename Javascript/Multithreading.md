---
Mutithreading
---

* Traditionally,  Javascript is single-threaded. To clarify better, this means that one single thread handles the event loop. For older browsers, the whole browser shared one single thread between all the tabs.

* Luckily, in 2009, Good thing in 2009, Javascript introduced a hot new toy, Web Workers, to deal with this problem.

* Web Workers definitions:

 *  Web Workers are Javascript scripts executed from an HTML page that runs on a background thread away from the main execution thread. Data is sent between the main thread and workers through messages. Since these workers run on a separate thread than the main execution thread
,programmers can utilize web workers to run process intensive tasks from the browser without creating blocking instances.

* How it works:

```
var worker = new Worker('worker.js'); // import worker.js
worker.postMessage('Hi Dale')// The data sent between the main thread and the workers are copied rather than shared. 
self.addEventListener('message', function(e) {
  var message = e.data + 'I miss you so much!';
  self.postMessage(message); //we are sending the message, ‘hi Dale I miss you so much!’ back to the main execution thread.
  self.close();
}
worker.addEventListener('message', function(e) {
  console.log(e.data);
}
worker.postMessage('Hi Dale')// The data sent between the main thread and the workers are copied rather than shared
```

* Summarizing the steps:
 *  Our application created a web worker in main.js which * runs the code from worker.js
 *  It sends the worker a message with the string ‘Hi Dale’
 *  The worker, which had an event listener for ‘message’,      received the message and ran the code within.
 *  The worker appended ‘to myself!’ to the message data creating ‘Hi Dale I miss you so much!’ and sends that as data within a message back tomain.js, which also had an event listener for message, than console.log ‘Hi Dale I miss you so much!’.
