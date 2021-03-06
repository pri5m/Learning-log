[lesson plan pdf](https://learningcentral.cf.ac.uk/bbcswebdav/pid-4466194-dt-content-rid-7931833_2/courses/1718-CM6112/LessonPlanDOM.pdf)

# Pre reading
[CSS tricks DOM](https://css-tricks.com/dom/)

[MDN Intro to the DOM](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model/Introduction)

# Videos
[DOM](https://learningcentral.cf.ac.uk/bbcswebdav/pid-4470037-dt-content-rid-7970398_2/xid-7970398_2)

[Events](https://learningcentral.cf.ac.uk/bbcswebdav/pid-4470037-dt-content-rid-7970399_2/xid-7970399_2)

# Slides

[Slides link](https://learningcentral.cf.ac.uk/bbcswebdav/pid-4470030-dt-content-rid-7970382_2/courses/1718-CM6112/DOM.pdf)

# Homework
[How Browsers Work: Behind the scenes of modern web browsers](https://www.html5rocks.com/en/tutorials/internals/howbrowserswork/)

[Video- Philip Roberts: What the heck is the event loop anyway? | JSConf EU 2014](https://www.youtube.com/watch?v=8aGhZQkoFbQ)
Javascript

**The call stack**

one thread == one call stack == one thing at a time

A data structure which recalls where in the program we are.

**blocking**

What happens when things are slow? eg. image processing, calling a really long while loop

Why is this a a problem? Because, browsers

The solution? asynchronous callbacks

call back- run some code, give it a pull back, and run it later

setTimeout(...) - call back function, timer in the webapi

**Concurrency and the event loop**

One thing at a time, except not really

Once the webapi is done with the processing, it pushes it to the task queue where it is held, ready to be used in the stack. It will be moved when the stack is ready, by the event loop

The event loops job is to look at the stack and to look at the task queue. If the stack is empty, it takes the first thig in the task queue and pushes it to the stack, which then runs it.

```
console.log('Hi);

setTimeout(function cb() {
    console.log('there');
}, 0);

console.log('JSConfEU');
```
Why set the time to zero? The webapi sends it straight to the task queue, where it has to wait until the event loop call it to be used in the stack. The main files are going to continue to run, while the item that had the time set to zero, has to wait until the stack has been cleared, running that item last. Defers the execution of the code until the rest of the stack has cleared.

setTimeout(...) is NOT a set time of execution, but a minimum time of execution. Just like when setTimeout is 0. It doesn't run the code imediately, but next.

Asynchronous- Allows render to take place in between each event loop, making it more useable, makes it more fluid.

The callbck queue can become backed up and make it run code slowly. Can be ways to stop this if the user stops scrolling down the browser, rendering what has already loaded, and then to continue to retrieve the rest of the web page.

[Loupe](http://latentflip.com/loupe/?code=JC5vbignYnV0dG9uJywgJ2NsaWNrJywgZnVuY3Rpb24gb25DbGljaygpIHsKICAgIHNldFRpbWVvdXQoZnVuY3Rpb24gdGltZXIoKSB7CiAgICAgICAgY29uc29sZS5sb2coJ1lvdSBjbGlja2VkIHRoZSBidXR0b24hJyk7ICAgIAogICAgfSwgMjAwMCk7Cn0pOwoKY29uc29sZS5sb2coIkhpISIpOwoKc2V0VGltZW91dChmdW5jdGlvbiB0aW1lb3V0KCkgewogICAgY29uc29sZS5sb2coIkNsaWNrIHRoZSBidXR0b24hIik7Cn0sIDUwMDApOwoKY29uc29sZS5sb2coIldlbGNvbWUgdG8gbG91cGUuIik7!!!PGJ1dHRvbj5DbGljayBtZSE8L2J1dHRvbj4%3D)
