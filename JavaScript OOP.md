# JavaScript-[JS-OOP](Object-Oriented Programming-JavaScript) :scream_cat: 
_Source: JS Object-Oriented Programming JavaScript - Udacity Front End Web Development Nanodegree_

WORKING ON IT!!

Object-Oriented JavaScript



a. Scopes
Lexical Scoping in JavaScript:
Execution Contexts ('in-memory scopes') in JavaScript:

b. Closures
Closures in JavaScript
'this' keyword
Passing a reference to 'this' with .call()
'extend()' vs. 'Object.create()'
Functional Class Definitions
Prototypical Class Definitions
Pseudoclassical Class Definitions
Superclass and Subclass Definitions (Functional Class stye)
Superclass and Subclass Definitions (Pseudoclassical Class style)
Bonus (advanced) example of closures
[Code examples for OOJS](https://github.com/batmanimal/object-oriented-js)

Scopes
Lexical Scoping in JavaScript:
'The region in your source code where you can refer to variables by name without getting access errors.'
New lexical scopes are created every time you make a new function definition (NOT in if statements).
Variables defined within a lexical scope cannot be accessed outside that scope.
Remember to use the var keyword when you make a new variable in a scope (it is not required by the language, but you should always do it! If you do not use var, the variable will be placed in the global namespace - don’t use this 'feature' to accomplish that, it’s bad).

The global scope is shared between (.js) files.

Execution Contexts ('in-memory scopes') in JavaScript:
A new execution context is created each time you run a function.

Closures
Closures in JavaScript
'A closure is any function that remains available after any outer scopes have returned.'
The most useful feature of closures is variable access, functions within an inner scope have access to variables defined in an outer scope:
function foo() {
 var fooVar = ‘A Variable!’;

 function bar() {
   console.log(fooVar); // fooVar is available here
 }
}
'this' keyword
generally_this_is_bound_to_v2.png


Passing a reference to 'this' with .call()
Either pass in an object and invoke the function or override by using .call() to literally pass in the reference you want to use for this

method_call_v2.png

'extend()' vs. 'Object.create()'
`extend()`= an _example function that copies all properties one-time_ 

Object.create()
creates an ongoing lookup to the parent object

Note: extend() doesn't exist in vanilla JS. 
Many libraries include this functionality because it's so useful (jQuery for instance, http://api.jquery.com/jquery.extend).

extend_vs_object_create_v2.png

Functional Class Definitions
functional_class_v1.png

Prototypical Class Definitions
prototypical_class_v1.png

Pseudoclassical Class Definitions
pseudoclassical_class_v1.png

Superclass and Subclass Definitions (Functional Class stye)
superclass_functional_v2.png

Superclass and Subclass Definitions (Pseudoclassical Class style)
superclass_pseudoclassical_v2.png

Here is the code for inherit if you want to copy it:
// pseudoclassical inheritance
// subClass will inherit from superClass
```
inherit = function(subClass,superClass) {
   subClass.prototype = Object.create(superClass.prototype); // delegate to prototype
   subClass.prototype.constructor = subClass; // set constructor on prototype
}
inherit(Van,Car);
```
[Pseudoclassical inheritance in JavaScript](http://phrogz.net/js/classes/OOPinJS2.html)
Example:
```
Van.inheritsFrom( Car );
```

Bonus (advanced) example of closures
Regarding the fooVar example above, we might ask: is fooVar frozen in time? That is, if fooVar were changed and accessed in a later call of bar(), would fooVar hold the original value or would it have the new value because fooVar is an ongoing lookup? The answer is that it will change because the lookup is ongoing. We can test this in the console of a browser with the use of setTimeout, printing the time and nesting some scopes in an extended version of the fooVar example above. Don’t worry if you don’t understand this, but if you’re curious, this will show you that the variables (eg. fooVar) in the execution context remain 'live', ie. they can be modified and will affect any scopes that have them in their closures. The intended way to understand this is to read the output first and then see what the code was doing to produce it, matching the printed statements to the code.


// zero padding by profitehlolz found on stack overflow:
// http://stackoverflow.com/questions/1267283/how-can-i-create-a-zerofilled-value-using-javascript
```
function zeropad(n, p, c) {
   var pad_char = typeof c !== 'undefined' ? c : '0';
   var pad = new Array(1 + p).join(pad_char);
   return (pad + n).slice(-pad.length);
}

function getTime(currentdate) {
   return currentdate.getHours() + ':'
       + zeropad(currentdate.getMinutes(),2) + ':'
       + zeropad(currentdate.getSeconds(),2);
}
console.log('TEST ' + getTime(new Date()));

var globalVar = 'globalVar ' + getTime(new Date());

function foo() {
   var fooVar = 'Foo Variable!', fooDate = new Date();
   console.log('Time in foo = ' + getTime(fooDate));

   function modGlobalVar() {
        globalVar = 'globalVar ' + getTime(new Date());
   }

   function bar() {
       console.log('----------');
       console.log('Time in bar = ' + getTime(fooDate));
       console.log('fooVar in bar = ' + fooVar); // fooVar is available here
       console.log('globalVar in bar = ' + globalVar);
       console.log('==========');
   }
   bar();
   console.log('\nThis test shows that fooVar can be changed after bar is defined and run.\n');
   fooVar = 'Foo Variable has been changed!';
   setTimeout(modGlobalVar,         2500); // modify globalVar before bar is called again
   setTimeout(bar,                 5000);
}
foo();
```
Produces this output (in Chrome’s JavaScript console):
TEST 10:48:04
Time in foo = 10:48:04
----------
Time in bar = 10:48:04
fooVar in bar = Foo Variable!
globalVar in bar = globalVar 10:48:04
==========

This test shows that fooVar can be changed after bar is defined and run.
----------
Time in bar = 10:48:04
fooVar in bar = Foo Variable has been changed!
globalVar in bar = globalVar 10:48:07
==========

 
 
#### Goals:
- JavaScript object fundamentals
- Object 
- First-class functions
- JavaScript's abstractions 

### Table Of Contents:
- a. JavaScript object fundamentals
- b. Objects: Create, access, and modify objects.
- c. Firs-class functions (JavaScript functions = first-class functions)
- d. Abstactions (over traditional classes and inheritance.)

1. [Objects In Depth](#objects-in-depth).
2. [Functions at runtime](#functions-at-runtime).
3. [Classes and Objects](#classes-and-objects).

### a. JavaScript object fundamentals
In JavaScript, an `object`= an _unordered collection of properties._ 
Each property consists of a `key/value pair`, and can `refer`to:
1) a __primitive__ 
- string
- number
- booleans

2) another __object__. 
Unlike elements in an array[], which are accessed by a numeric index, 
properties in objects are accessed by their key name using either {}square bracket notation or . dot notation.

### b. Objects in Depth
__Object Definition:__  a collection of associated unordered (opposite to arrays) key/value pairs. 
It is defined with curly brackets `{}`. 
Key/value pairs are called properties. 
They (key/value) is connected using colon `:` 
Properties separated from each other using comma `,` 

- Syntax: 
const course = { courseId: 711 }; 
const course = { 'courseId': 711 }; 
const course = { "courseId": 711 };

As you see the key string can be with or without quotes. 
Mostly without quotes but are essential in certain cases: 
- reserved word (e.g., for, if, let, true, etc.).
- Contains spaces or special characters that cannot appear in a variable name.
- Accessing object properties values:

  - Using `dot notation` : `course.courseId;`
  Limitations:
  1. When the key is a number.
  2. When the key is stored in a variable and we want to access this property by the variable.
  - Using `bracket notation` : `course['courseId'];`
  
- Accessing nested object properties values:

```
const bicycle = {
  color: 'blue',
  type: 'mountain bike',
  wheels: {
    diameter: 18,
    width: 8
  }
};

bicycle.wheels.width;
```

### c. Firs-class functions (JavaScript functions = first-class functions)
### d. Abstactions (over traditional classes and inheritance.)

#### Resources 
- [Further Research]()
- [Intro to JavaScript](https://eu.udacity.com/course/intro-to-javascript--ud803)
- [Unquoted property names / object keys in JavaScript](https://mathiasbynens.be/notes/javascript-properties)
- [Valid JavaScript variable names in ECMAScript 5](https://mathiasbynens.be/notes/javascript-identifiers)
- [Valid JavaScript variable names in ECMAScript 6](https://mathiasbynens.be/notes/javascript-identifiers-es6)


- How to read existing properties in an object? 
- How to modifying existing properties?
- How to add and remove properties?


### Creating and modifying objects
- [A link to the course page](https://classroom.udacity.com/nanodegrees/nd001/parts/4942f4d7-a48d-4794-9eb0-404b3ed3cfe1/modules/7e56389b-50d8-4e3a-84a0-eb3fd45456b2/lessons/504843ae-ba16-4573-a859-94da7a7d1dd4/concepts/2bbcfed5-e683-431b-ace2-b67c091400d2).
- Create: 
```
// Using literal notation:
const myObject = {};

// Using the Object() constructor function (slower):
const myObject = new Object();

//Using constructor function:
function MyObjectConstructor() {
  }
const myObject = new MyObjectConstructor();
```

- Modifying object properties
```
const cat = {
  age: 2,
  name: 'Bailey'
}
cat.age += 1;

cat.age;
// 3

cat.name = 'Bambi';

cat.name;
// 'Bambi'
```

- Adding Object properties
```
const printer = {};

printer.on = true;
printer.mode = 'black and white';
printer.print = function () {
  console.log('The printer is printing!');
};
```

- Removing Object properties
```
delete printer.mode;
// true
```

- Since Objects are passed by reference, making changes to an original object make the same change to its copy
```
const iceCreamOriginal = {
  Andrew: 3,
  Richard: 15
};

const iceCreamCopy = iceCreamOriginal;

iceCreamCopy.Richard;
// 15

iceCreamCopy.Richard = 99;

iceCreamCopy.Richard;
// 99

iceCreamOriginal.Richard;
// 99
```

- Comparing an Object with Another Object

```
const object1 = {
  name: bird}
const object2 = {
  name: bird}
object1 === object2;//false

const object = object1;
object;//{name: bird}

object === object1;//true. Also any change in object1 will make the same change in object.
object === object2;//false.
```
### Invoke object method

- invoke methods different ways

```
const developer = {
  sayHello: function () {
    console.log('Hi there!');
  }
};
developer.sayHello();//Hi there!
developer['sayHello']();//Hi there!
```

- passing arguments into methods

```
const developer = {
  name: 'Andrew',
  favoriteLanguage: function (language) {
    console.log(`My name is ${this.name} and my favorite programming language is ${language}.`);
  }
};

developer.favoriteLanguage('JavaScript');//My name is Andrew and my favorite programming language is JavaScript.
```
- Naming properties functions ( rather than using anonymous functions) is valid and is useful for debugging.


