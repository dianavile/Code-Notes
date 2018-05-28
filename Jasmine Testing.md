## Jasmine-Testing (Lesson 22)
- Javascript doesn´t have `unix test` functions by default. 
- Therefore the _popular, easy to use_ [Jasmine Library](https://jasmine.github.io/)(version 2.2) is needed.
- The way to organize a test is up to you and your preferences. No right or wrong way.

## Jasmine Syntax:
- __EXAMPLE CODE:__
```
describe("A suite", function() {
  it("contains spec with an expectation", function() {
    expect(true).toBe(true);
  });
});
```
- 1) `Describe()` calls = colored __black__
_describe()_ calls are black, they are used to identify a suite which is a group of related specs.
```
describe("Player", function() {
  var player;
  var song;
```
- 2) `It()` calls= colored _green!_
_it()_ calls are green, they are used to identify a **spec**ification
                        just a container for a test
                        _if all expectations within a spec are **true**, then that spec passes, else it will **fail**_
```
  it(´should be able to play a Song´, function() {
    player.play(song);
    expect(player.currentlyPlayingSong).toEqual(song);
```
## Organize a test: Introducing Specs and Suites
`Describe` and `It` are used to create an __outline__ to __ORGANIZE information__.

### Specs 
- `It` = used to create a __specification(SPEC)__. 
- A `spec` = a _container_ for a __test__, to identify the exact feature to test.
-  `Spec passes`=__If all exceptations(spec) within a spec return "TRUE"__.
-  `Spec fails`=__If any of the exceptations(spec) within a spec returns "FALSE"__.
- `It`= to define the _boundry to its test._

### Suites 
- `Describe` = used to identify a __suite(SUITE)__. 
- a `Suite`= a __group of related specs__.
- Everything contained within this block of code is related to the Suite (e.g.´Player´).
- It is a level of `indentation`.

## Write a test:
Start with _a call to expect_ - **expect()**
Follow a comparison method / _matcher_ - **toBe()** or **not.toBe()**

`expect(add(0.1, 0.2)).toBe(0.3);`

- (1) The __launching point__ of any test to _start the test process_: each test start with a call to `expect`. 
- (2) The __process function__ excepts a _single value_, called the `actual`, to test.
- (3) The __comparision method__ called the `matcher`, it is chained after the call to expect. 
      Example: `.toBe` = equivalant to "strict=comparison".
- (4) The __expected value__ what you expect the process function with the comparision methd to `return`.


- If this expression returns `true`= Test `passes`:
`expect(add(0.1, 0.2)).toBe(0.3);`
= `(add(0.1, 0.2)) === (0.3);` 

- If this expression returns `false`= Test `do NOT pass`. 
Or to __negate a test__ (test expression = `false`)
```
expect(add(0.1, 0.2)).not.toBe(0.1);
```
## Quiz: Would this spec pass or fail?
- A spec can contain multiple test, but each test must return `true` for the spec to `pass` the test.
```
 it(´should consider this spec´.function() {
    expect(true).toBe(true);
    expect(false).not.toBe(false); 
```
- This spec would `fail` because our second test is returning `false`.

## Error handling - Getting Started with Red-Green-Refactor-cycle
_**It is important to write your test before you begin to code!**_

```
function add(x, y) {
    if (typeof x && typeof y !== 'number') {
        trhow new Error('Param must be a number');
    }
    return x + y;
}
```
- Write your test first.
- They all fail, since there is no code to make them pass.
- Then you go write your code to make your test pass.
- Once that is complete, you can safely refactor your code, as you continue to add new features.

```
describe('Address Book', function() {
	it('should be able to add a contact', function() {
		var addressBook = new AddressBook();
			thisContact = new Contact();

			addressBook.addContact(thisContact);

			expect(adressBook.getContact(0)).toBe(thisContact);
	}); 
});
```
## Writing our Implementation
- raise exceptions: 1 spec, 1 failure
- Address Book should be able to add a contact
- __Error:__ Address Book is not defined

__In what file would i write my implementation?__
- [] spec/AddressBookSpec.js = __TEST FILE__
- [] src/Contact.js          = __implementation of TEST in a ContactSpec.js__
- [x] src/AddressBook.js     = 

 - Write all of our application code within the `src/ directory` 
 - Name it `AddressBook.js` since that's the most accurate name for the functionality contained within.

## Another Spec

## Async JavaScript Testing
- Since JavaScript is the language of the web, there are some functions that by necessity are going to take a decent amount of time to complete, such as fetching data from a server to display on your site. 
- For this reason, JavaScript includes support for 
- `asynchronous functions` = _functions that can happen in the background while the rest of your code executes._

### Callbacks
- This was most commonly handled with `callbacks`. This is still used a lot in certain circumstances.
- A `callback` function() = _a function passed into another function as an argument, which is then invoked inside the outer function to complete some kind of routine or action._[Callback function- MDN](https://developer.mozilla.org/en-US/docs/Glossary/Callback_function)

- `Callbacks`= functions that get passed into other functions. 
For example:
```
myDiv.addEventListener("click", function(){
  // do something!
})
```
- The __function__ `addEventListener()` takes a __callback__ `the “do something” function)` and __calls it when__ `myDiv` gets clicked.

- Unfortunately, though they are useful in situations like the above example, using callbacks can get out of hand, especially when you need to chain several of them together in a specific order. 

#### Resources Callback
- [Callback-Hell](http://callbackhell.com/)
- [Article](https://github.com/maxogden/art-of-node#callbacks)
- [Video](https://www.youtube.com/watch?v=QRq2zMHlBz4)

### Promises
- A `promise`= an _object that might produce a value at some point in the future._ 

Example:
- getData() is a function that fetches some data from a server 
- And returns it as an object that we can use in our code:
```
const getData = function() {
  // go fetch data from some API...
  // clean it up a bit and return it as an object:
  return data
}
``` 
__NOTE:__ The issue with this example = it  __takes time to fetch the data__, but unless we tell our code that, it assumes that everything in the function happens essentially instantly. 
So, this will give a problem, because when we try to extract pieceOfData out of the returned data, the function getData() will most likely still be fetching, so myData will not be the expected data, but will be __undefined__:
```
const myData = getData()
const pieceOfData = myData['whatever']
```
To solve this problem:
- tell the code to wait until the data is done fetching to continue. 
- This can be done with `Promises`. It allows you to do this:
```
const myData = getData() // if this is refactored to return a Promise...

myData.then(function(data){ // .then() tells it to wait until the promise is resolved
  const pieceOfData = data['whatever'] // and THEN run the function inside
})
```
- [Jasmine Documentation](https://jasmine.github.io/2.1/introduction.html)