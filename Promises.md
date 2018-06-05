# Callback, Promises & Async

__Callback__ = `the default JS technique for Asynchronous work`: 
- Passes a `function`() into another function 
- Calls the `call back`() function at some time later, when some conditions have been met.
- __EXAMPLE:__
```
function loadImage(scr, parent, callback) {
 var img = document.createElement('img');
 img.src = src;
 img.onload = callback;
 parent.appendChild(img);
};
```
- __NOTE:__ Althoug a `callback() function` works fine, it is not a solution for everything:

## Callbacks vs Thens
Remaining questions are: __Any operation could fail at any time__

1) __How to handle errors?__ 
- JavaScript error: `undefined is not a function`.
- Network error: `network request error`.
__NOTE:__ Althoug Node.js makes Async obligatory, but it is still the full responsibility of the coder to __define and implement a code error strategy__.

2) __How to create a work sequence?__

- Instead of creating a function into another function into another callback function, - known as the __Paramid of DOOM__, 
- it is better to create a good work sequence.
- __EXAMPLE: Paramid of DOOM__
```
loadImage('above-the-fold.jpg', imgContainer, function() {
  loadImage('just-below-the-fold.jpg', imgContainer2, function() {
   loadImage('further-down-fold.jpg', imgContainer3, function() {
    loadImage('this-is-ridiculous.jpg', imgContainer4, function() {
     loadImage('abstract-art.jpg', imgContainer5, function() {
      loadImage('egyptian-pyramids.jpg', imgContainer6, function() {
       loadImage('last-below-the-fold.jpg', imgContainer7, function() {
        })
       })
      })
     })
    })
   })
  })
 })
})
```
# Promises 
- Now see the same kind of code written with Promises.

- __EXAMPLE: Promises__
```
var sequence = get('example.json')
 .then(doSomething)
 .then(doSomethingElse);
```
- This is so much easier!

__Course Stages:__
1. Wrapping.
2. Thening.
3. Catching.
4. Chaining.

__States:__
1. Fulfilled (Resolved). => The action related to the promise succeeded.
2. Rejected. => The action related to the promise failed.
3. Pending. => Promise has not yet fulfilled or rejected.
4. Settled. => Promise has either fulfilled or rejected.

 # Async/Await
 ![Async](https://github.com/dianavile/Code-Notes/blob/master/img/Async.png)
 
# Resources:
- [Getting to know asynchronous JavaScript: Callbacks, Promises and Async/Await](https://medium.com/codebuddies/getting-to-know-asynchronous-javascript-callbacks-promises-and-async-await-17e0673281ee)
- [JavaScript Promises](https://davidwalsh.name/promises)
- [Google Developers- JavaScript Promises: an Introduction](https://developers.google.com/web/fundamentals/primers/promises)
- [JavaScript Promises for Dummies](https://scotch.io/tutorials/javascript-promises-for-dummies)
- [Asynchronous vs synchronous execution, what does it really mean?](https://stackoverflow.com/questions/748175/asynchronous-vs-synchronous-execution-what-does-it-really-mean)
- [The Future of JavaScript]()
