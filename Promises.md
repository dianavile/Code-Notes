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

__PROMISES Course Stages:__
1. Wrapping stage= `the syntax of constructing promises`.
2. Thening stage = `How to react to the resolution of a promise`: __ACTIONS__ TO TAKE.
3. Catching stage = `If something breaks, catch the error`: __RECOVERY__ TO MAKE.
4. Chaining stage =  `Create a long sequences of asynchronous work`: __ASYNC__ TO MAKE. 

__PROMISES States:__
1. Fulfilled (Resolved). => The action related to `the promise succeeded`.  __RESOLVED__: It works.
2. Rejected. => The action related to `the promise failed`.  __REJECTED__: It DOES NOT work.
3. Pending. => Promise has `not yet fulfilled or rejected`.  __PENDING__: It is still waiting.
4. Settled. => Promise has `either fulfilled or rejected`.  __SETTLED__: Something happened.


__EXAMPLE__: Promises
- First the Event fires
- Second set The Event listerer
```
new Promise(function(resolve, reject) {
  resolve('hi'); // works
  resolve('bye');// can´t happen a second time
});
```
__Promise resolves__
- First: Promise created
- Second: Promis settled
- Set action for resolution value = //on main thread and potentially "blocking"
Promise
```
Try{
}.....{
....
}
```

### __Async Scenarios: When to use Promises__
When and where Promises are useful: 
EXAMPLE 1: Promises = useful
```
var data = get ('data.json');
data.onload = fucntion (){
analyze(this.responseText);
};
```
EXAMPLE 2: Promises = NOT NEEDED
```
hugeArrayOfImages.forEach(function(i) {
  makeSepia(i);
  });
```
EXAMPLE 3: Promises = NOT NEEDED
```
data.forEach(function(d) {
 var div = createDiv(d);
 body.appendChild(div);
});
```
EXAMPLE 4: Promises = useful
```
var worker = new Worker ('worker.js');
 worker.postMessage/data);
 worker.onmmessage = doSomething;
```
- __EXAMPLE: Promises= UNDEFINED__
```
new Promise(function(resolve) {
  console.log('first');
  resolve();
  console.log('second');
}).then(function() {
  console.log('third');
});
```
Promise {<resolved>: undefined}

- You'll notice that `'first'`, `'second'` and `'third'` all get logged. 
- `'second'` gets logged despite that it comes after `resolve()`.
- Pass a value or `undefined` through `resolve()` and `reject()` to `.then` and `.catch.` 
- The values aren't being passed to `.then` or `.catch`, but to __the functions called by__ `.then` or `.catch`.


 # Async/Await
 ![Async](https://github.com/dianavile/Code-Notes/blob/master/img/Async.png)
 
# Resources:
- [Getting to know asynchronous JavaScript: Callbacks, Promises and Async/Await](https://medium.com/codebuddies/getting-to-know-asynchronous-javascript-callbacks-promises-and-async-await-17e0673281ee)
- [JavaScript Promises](https://davidwalsh.name/promises)
- [Google Developers- JavaScript Promises: an Introduction](https://developers.google.com/web/fundamentals/primers/promises)
- [JavaScript Promises for Dummies](https://scotch.io/tutorials/javascript-promises-for-dummies)
- [Asynchronous vs synchronous execution, what does it really mean?](https://stackoverflow.com/questions/748175/asynchronous-vs-synchronous-execution-what-does-it-really-mean)
- [The Future of JavaScript](https://github.com/dianavile/Code-Notes/blob/master/img/future_of_js_2018_progress.pdf)
- [Asynchronous JavaScript #1 - What is Asynchronous JavaScript?](https://www.youtube.com/watch?v=YxWMxJONp7E&list=PL4cUxeGkcC9jAhrjtZ9U93UMIhnCc44MH)
