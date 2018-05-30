# Default Function Parameters

In case of:
```
function sayHi (name, greeting) {
  return `${greeting} ${name}`;}
  
sayHi('Diana', 'Hi');//Hi Diana
sayHu();//Uncaught ReferenceError: sayHu is not defined at ...
```

You can write
```
function sayHi (name, greeting) {
name = (name !== undefined)? name : 'Islam';
greeting = (greeting !== undefined)? greeting : 'Hi'
  return `${greeting} ${name}`;}
  
sayHi();// Hi Diana
sayHi('Monica', 'Hello');//Hello Monica
```

So you can write this instead:
```
function sayHi (name = 'Diana', greeting = 'Hi') {
  return `${greeting} ${name}`;}
  
sayHi();// Hi Diana
sayHi('Monica', 'Hello');//Hello Monica
```

This is `default function parameters`= __Assigning a default values for function parameters__ in case __no values are assigned__ when invoking the function. 
