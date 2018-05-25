# ES6 Built-ins

Description: _This is an index for the files notes of Built-ins lesson of Udacity Front End Nanodegree course._

### Table of Contents:

1. [symbols](https://github.com/Islam888/Study-Notes/blob/master/JS/symbols.md).
2. [Object Iteration](https://github.com/Islam888/Study-Notes/blob/master/JS/Object%20Iteration.md).

# symbols: 
- A new JS primitive data type.(number, string, boolean, null, undefined, symbol)
- is "unique, and immutable data type that is used to identify object properties".
- created by invoking Symbol() function.
- Symbol('description') function can have an optional string description that is used for _debugging_.
- Description is a way to describe the created symbol. It can not access the symbol or affect its value. That's why the symbols with the same description are not equal.
- syntax:
  ```javascript
  
  const bowl = {
  [Symbol('apple')]: { color: 'red', weight: 136.078 },
  [Symbol('banana')]: { color: 'yellow', weight: 183.15 },
  [Symbol('orange')]: { color: 'orange', weight: 170.097 },
  [Symbol('banana')]: { color: 'yellow', weight: 176.845 }
  };
  console.log(bowl);//{Symbol(apple): {…}, Symbol(banana): {…}, Symbol(orange): {…}, Symbol(banana): {…}}
  
  # Object Iteration

### Table of Contents:

1. [Description](#description).
2. [Iterable Protocol](#iterable-protocol).

### Description:

- This will show us "**How to iterate over an object**".

### Iterable Protocol

- **Definition**: define and customize the iteration behavior of objects (which are not iterables). This means that now we have the flexibility of defining and customizing this iteration behavior for objects.
- Using `[Symbol.iterator]()`


### Iterator Protocol

- **Definition**: define a standard way that an object produces a sequence of values (how an object will iterate).
- Using `next()`

----------------------------


- So for an object to be iterable ---must implement---> iterator method(define how object will be iterated).
- Our iterator method here is `[Symbol.iterator]()`
- `[Symbol.iterator]()` is a zero argument method ---returns---> iterator object (which is an object that conforms to iterator protocol).
- On iterator object, you can call method `next()`
- `next()` method is a zero argument method that returns an object with 2 properties:
    1. `value`: value returned by the iterator. `undefined` when the iterator past the end of the iterated sequence (past the last value of the object).
    2. `done`: (boolean) which can be true or false. `true` if the iterator past the end of the iterated sequence (past the last value of the object). `false` if the iterator was able to produce the next value in the sequence (still there is a value or values to produce).


```javascript
const digits = [0, 1, 2];
const arrayIterator = digits[Symbol.iterator]();

console.log(arrayIterator.next());//Object {value: 0, done: false}
console.log(arrayIterator.next());//Object {value: 1, done: false}
console.log(arrayIterator.next());//Object {value: 2, done: false}
console.log(arrayIterator.next());//Object {value: undefined, done: true}
```