# JavaScript-[Array-JS](-Array-JavaScript)
_Source: Array JavaScript - Udacity Front End Web Development Nanodegree_


### Table Of Contents:
- a. __What is an Array?__
- b. __Create an Array__
- c. __Store different types of data__
- d. __Array Properties and Methods__
- e. __Array.length__


- f. 
- g. 
- h. 

### a. What is an Array?
- An __array__ `[]` = `ordered collection of elements, enclosed by square brackets (i.e., [ and ]).`
- It is one of the most useful data structures in JavaScript, because it stores __multiple values into a single, organized data structure.__ 

### b. Create an Array
- You can define a new array by listing values _separated with commas_ `,` between _square brackets_ `[]`.
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
// 'apple'
- To access the __last (right-most) element__ in "fruits",use its `index`:
```
fruits[4];
```
// 'lychee'

### c. Store different types of data
// Create a `donuts` array with three strings
  * __A `string`__
```
var donuts = ["glazed", "powdered", "jelly"];
```  
- Arrays[] can store many different types of data, not only strings!
// creates a `mixedData` array with mixed data types
  * __A `number`__
  * __A `boolean`__
```
var mixedData = ["abcd", 1, true, undefined, null, "all the things"];
```
// creates a `arraysInArrays` array with three arrays:
  * __Another array `nested array`__ 
- Store an array in an array to create a nested array!

```
var arraysInArrays = [[1, 2, 3], ["Julia", "James"], [true, false, true, false]];
```
- Nested arrays can be particularly hard to read, so it's common to write them on one line, using a newline after each comma:
```
var arraysInArrays = [
  [1, 2, 3], 
  ["Julia", "James"], 
  [true, false, true, false]
];
```
- d. __Array Properties and Methods__

- e. __Array.length__
Find the length of an array by using its length property.
```
var donuts = ["glazed", "powdered", "sprinkled"];
console.log(donuts.length);
```

#### Resources 
- [Array](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array)

#### Take Away
