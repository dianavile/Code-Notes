# JavaScript-[Array-JS](-Array-JavaScript)
_Source: Array JavaScript - Udacity Front End Web Development Nanodegree_


### Table Of Contents:
- a. __What is an Array?__
- b. __Create an Array__
- c. __Store different types of data__
- d. __Array Properties and Methods__
- e. __Property: .length__ 
- f. __push() method__ 
- g. __pop() method__
- h. __slice/splice() method__
- i. __Array Loops__
- j. __For Loop__
- k. __Map__
- l. __2D Grid(nested array)__

### a. What is an Array?
- An __array__ `[]` = _ordered collection of elements, enclosed by square brackets []._
- It is one of the most useful data structures in JavaScript, as it stores __multiple values into a single, organized data structure.__ 

### b. Create an Array
- Define a new array by _listing values_ _separated with commas_ `,` between _square brackets_ `[]`.
- __Example:__  variable "myArray", assigned to an empty array:
```
const myArray = [];
```
- Each element in an array is referenced by a __numeric key__ (`index`).
- It starts from zero and increments by one for each additional element in the array. 
- __Example:__ 
```
const fruits = ['apple', 'banana', 'orange', 'grape', 'lychee'];
console.log(fruits);
```
// ['apple', 'banana', 'orange', 'grape', `lychee`]

- To access the __first (left-most) element__ in "fruits", access that element by its `index`:
```
fruits[0];
```
//= 'apple'
- To access the __last (right-most) element__ in "fruits",use its `index`:
```
fruits[4];
```
//= 'lychee'

### c. Store different types of data
- Arrays[] can store __different types of data__, not only strings!

// Create a `donuts` array with three strings
  * __A `string`__
```
var donuts = ["glazed", "powdered", "jelly"];
```  
// Create a `mixedData` array with mixed data types
  * __A `number`__
  * __A `boolean`__
```
var mixedData = ["abcd", 1, true, undefined, null, "all the things"];
```
// Create a `arraysInArrays` array with three arrays:
  * __Another array `nested array`__: store an array in an array to create a `nested array`
```
var arraysInArrays = [[1, 2, 3], ["Julia", "James"], [true, false, true, false]];
```
- Nested arrays can be hard to read. So, write them on one line, using a newline after each comma:
```
var arraysInArrays = [
  [1, 2, 3], 
  ["Julia", "James"], 
  [true, false, true, false]
];
```
### d. __Array Properties and Methods__
built-in methods

### e. __Array Property: .length__ (=to find length of an array)
- Find the __length of an array__ by using its length property. `.lenght`
- To access the length property, type the name of the array, followed by a period .
- The length property will then return the number of elements in the array.
```
var donuts = ["glazed", "powdered", "sprinkled"];
console.log(donuts.length);
```
__TIP:__ Strings have a length property too! Use it to get the length of any string. 
Example
```
"supercalifragilisticexpialidocious".length 
```
returns 34.

### f. __push() method__ (=to "add" elements to the end of an array.)
- The two most common methods for __modifying an array__ are 
  1) `push()` to add an element to the end of an Array[] = `arr.push(element1[, ...[, elementN]])`
- __Example:__ _Represent the spread of donuts using an array_
```
var donuts = ["glazed", "chocolate frosted", "Boston creme", "glazed cruller", "cinnamon sugar", "sprinkled"];
```
// Push donuts onto the __end of the array__ using the push() method= pushes "powdered" onto the end of the `donuts` array
```
donuts.push("powdered"); 
```
// the `push()` method returns 7 because the `donuts` array now has 7 elements
Returns: 7
```
donuts array: ["glazed", "chocolate frosted", "Boston creme", "glazed cruller", "cinnamon sugar", "sprinkled", "powdered"]
```
```
var donuts = ["glazed", "chocolate frosted", "Boston creme", "glazed cruller", "cinnamon sugar", "sprinkled"];
donuts.push("powdered"); 
```
__NOTE:__ 
  1) with the `push() method` you need to pass the value of the element you want to add to the end of the array. 
  2) The `push() method` returns the length of the array after an element has been added.

### g. __pop() method__ (=to "remove" elements from the end of an array) 
  2) `pop()` to remove an element from the end of an Array[] = `arr.pop()`
  - __Example:__
```
var donuts = ["glazed", "chocolate frosted", "Boston creme", "glazed cruller", "cinnamon sugar", "sprinkled", "powdered"];
```
```
donuts.pop(); // pops "powdered" off the end of the `donuts` array
donuts.pop(); // pops "sprinkled" off the end of the `donuts` array
donuts.pop(); // pops "cinnamon sugar" off the end of the `donuts` array
```
Returns: "cinnamon sugar"
```
donuts array: ["glazed", "chocolate frosted", "Boston creme", "glazed cruller"]
```
__NOTE:__ 
- With the pop() method there is __NO__ need to _pass a value_ 
- pop() will __always remove the last element from the end of the array.__ 
- pop() _returns the element that has been removed_ in case you need to use it.

```
var donuts = ["glazed", "chocolate frosted", "Boston creme", "glazed cruller", "cinnamon sugar", "sprinkled", "powdered"];
donuts.pop(); 
```
// the `pop()` method returns "powdered" because "powdered" was the last element on the end of `donuts` array
- Returns: "powdered"

### h. __Array: splice() method__: (to add and remove elements from _anywhere within_ an array).
- The `splice()` method = to `add and remove elements from anywhere within an array`.
- It specify the index location to add new elements
- It specify the number of elements to delete (if any).
- The __first argument__ represents the `starting index` from where to change the array
- The __second argument__ represents the `elements to remove`
- The __remaining arguments__ represent the `elements to add`.
- Using the splice() method adds and removes elements from any location in an array.
- splice() is an incredibly powerful method that allows you to manipulate your arrays in a variety of ways. 
- Any combination of adding or removing elements from an array can all be done in one simple line of code.
```
var donuts = ["glazed", "chocolate frosted", "Boston creme", "glazed cruller"];
donuts.splice(1, 1, "chocolate cruller", "creme de leche"); 
```
// removes "chocolate frosted" at index 1 and adds "chocolate cruller" and "creme de leche" starting at index 1
- Returns: ["chocolate frosted"]
```
donuts array: ["glazed", "chocolate cruller", "creme de leche", "Boston creme", "glazed cruller"]
```
 ### i. __Array Loops__
Use a `loop`= to _efficiently access and manipulate each element in the array without writing repetitive code for each element_.
```
var donuts = ["jelly donut", "chocolate donut", "glazed donut"];
```
// Manually= make all the same donut types, but only sell them as donut holes instead
```
donuts[0] += " hole";
donuts[1] += " hole";
donuts[2] += " hole";
donuts array: ["jelly donut hole", "chocolate donut hole", "glazed donut hole"]
```
- //or `Loop through an array`
- //use a variable to represent the index in the array, and loop over that index to perform whatever manipulations desired.
```
var donuts = ["jelly donut", "chocolate donut", "glazed donut"];
```
- // the variable `i` is used to step through each element in the array
- // As i is incremented, step over each element in the array starting from 0 until donuts.length - 1 (donuts.length is out of bounds).
``` 
for (var i = 0; i < donuts.length; i++) {
    donuts[i] += " hole";
    donuts[i] = donuts[i].toUpperCase();
}
donuts array: ["JELLY DONUT HOLE", "CHOCOLATE DONUT HOLE", "GLAZED DONUT HOLE"]
```
### j. __The forEach() loop__
- Arrays have __special methods__ to help `iterate over` and `perform operations` on collections of data.
- The `forEach() method` gives an alternative way to iterate over an array, and manipulate each element in the array with an inline function expression.
```
var donuts = ["jelly donut", "chocolate donut", "glazed donut"];
```
- //donut corresponds to the element in the array itself. 
```
donuts.forEach(function(donut) {
  donut += " hole";
  donut = donut.toUpperCase();
  console.log(donut);
});
```
__Prints:__
- JELLY DONUT HOLE
- CHOCOLATE DONUT HOLE
- GLAZED DONUT HOLE
__NOTE:__ the forEach() method iterates over the array __without an explicitly defined__ index. 
- This is different from a `for` or `while loop`, where an __index is used to access _each element_ in the array__:
```
for (var i = 0; i < donuts.length; i++) {
  donuts[i] += " hole";
  donuts[i] = donuts[i].toUpperCase();
  console.log(donuts[i]);
}
```
__Parameters__
- The function that you pass to the forEach() method can take up to three parameters (`element`, `index`, and `array`).
- The `forEach() method` __call this function__ _once for each element in the array_ (forEach.) 
- Each time, it call the function with different arguments. 
- The `element` parameter get = the `value` of the array element. 
- The `index` parameter get = the `index` of the element (starting with zero). 
- The `array` parameter get = `reference to the whole array` (to modify the elements).
__Example:__
```
words = ["cat", "in", "hat"];
words.forEach(function(word, num, all) {
  console.log("Word " + num + " in " + all.toString() + " is " + word);
});
```
Prints:
- Word 0 in cat,in,hat is cat
- Word 1 in cat,in,hat is in
- Word 2 in cat,in,hat is hat
_ __NOTE___
 - Using forEach() will not be useful if you want to __permanently modify__ the original array. 
 - forEach() always returns undefined. 
 
 ### k. __The map() method__
- Use the map() method, to create a new array from an existing array.
- To take an array, perform an operation on each element of the array, and return a new array.
- The map() method accepts one argument (=a `function expression`, to manipulate each element in the array). 
- No longer `iterate over the indices`, because the map() does all that already.
```
var donuts = ["jelly donut", "chocolate donut", "glazed donut"];

var improvedDonuts = donuts.map(function(donut) {
  donut += " hole";
  donut = donut.toUpperCase();
  return donut;
});
donuts array: ["jelly donut", "chocolate donut", "glazed donut"]
improvedDonuts array: ["JELLY DONUT HOLE", "CHOCOLATE DONUT HOLE", "GLAZED DONUT HOLE"]
```
 ### l. __2D Grid(nested array)__
- Use an array of arrays that has the name of each donut associated with its position in the box.

- //Create a two dimensional grid with rows and columns.
- __Example:__
```
var donutBox = [
  ["glazed", "chocolate glazed", "cinnamon"],
  ["powdered", "sprinkled", "glazed cruller"],
  ["chocolate cruller", "Boston creme", "creme de leche"]
];
```
- //Loop over the donut box and display each donut (along with position in the box!) 
-  //__step 1:__ __Write a `for loop` to _loop over each row of the box__ of donuts_:
```
var donutBox = [
  ["glazed", "chocolate glazed", "cinnamon"],
  ["powdered", "sprinkled", "glazed cruller"],
  ["chocolate cruller", "Boston creme", "creme de leche"]
];
```
- // here, donutBox.length refers to the number of rows of donuts
```
for (var row = 0; row < donutBox.length; row++) {
  console.log(donutBox[row]);
}
```
_ Prints:
- ["glazed", "chocolate glazed", "cinnamon"]
- ["powdered", "sprinkled", "glazed cruller"]
- ["chocolate cruller", "Boston creme", "creme de leche"]

- //__step 2:__ Each row is an array of donuts. __Set up an `inner-loop` to _loop over each cell in the arrays_.__
```
for (var row = 0; row < donutBox.length; row++) {
```
- // here, donutBox[row].length refers to __the length of the donut array currently being looped over__
```
  for (var column = 0; column < donutBox[row].length; column++) {
    console.log(donutBox[row][column]);
  }
}
```
- __Prints:__
- "glazed"
- "chocolate glazed"
- "cinnamon"
- "powdered"
- "sprinkled"
- "glazed cruller"
- "chocolate cruller"
- "Boston creme"
- "creme de leche"

 ### Nested Array = Multi-dimensional arrays
- Arrays can be nested= an array can contain another array as an element. 
- Using this characteristic of JavaScript arrays, `multi-dimensional arrays` can be created.

The following code creates a __two-dimensional array.__
```
var a = new Array(4);
for (i = 0; i < 4; i++) {
  a[i] = new Array(4);
  for (j = 0; j < 4; j++) {
    a[i][j] = '[' + i + ', ' + j + ']';
  }
}
```
This example creates an array with the following rows:
```
Row 0: [0, 0] [0, 1] [0, 2] [0, 3]
Row 1: [1, 0] [1, 1] [1, 2] [1, 3]
Row 2: [2, 0] [2, 1] [2, 2] [2, 3]
Row 3: [3, 0] [3, 1] [3, 2] [3, 3]
```

#### Resources 
- [Array](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array)
- [Push()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/push)
- [Pop()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/pop)
- [Splice()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/splice)
- [forEach()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach)
- [map()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map)
- [2D Grid/nested array/Multi-dimensional arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Indexed_collections)

#### Take Away
- An `array[]` = _ordered collection of elements, enclosed by []._
- It stores __multiple values into a single, organized data structure.__ 
- `push()`method: add elements to the end of an array
- `pop()`method: remove elements from the end of an array
- `splice()`method: add and remove elements from anywhere within an array.
- `forEach() method` __call the function__ _once for each element in the array_ (forEach.), with different arguments:
  - `element` parameter get = the `value` of the array element. 
  - `index` parameter get = the `index` of the element (starting with zero). 
  - `array` parameter get = `reference to the whole array` (to modify the elements).
- `map()` method: create a new array from an existing array.
- `Arrays[]` can be nested= an array can contain another array as an element. 
