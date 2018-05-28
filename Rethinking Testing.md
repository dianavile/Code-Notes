## Rethinking Testing (Lesson 21)

### Description
- Why writing test is an important part of any project
- Get started writing your own tests.

### What is a Test?
- `Test driven development`.
- `Test`= validating an expectation.

### Always Failing
- A test that can not be passed, for a test give only results, is the test fails.
- Failure is the only option= validation an expectation about something.
- Failing a test is NOT BAD. 
- Test failure help you build bug-free apps with confidence. 

### Quiz: Validating an Opinion
- What expectation was the teacher testing?
-[] A) Students were studying for the test
-[X] B) Teacher taught material sufficiently
-[] C) Student attended class each day.
- Answer: Thanks for completing that!
The teacher expects they had taught the material sufficiently and is testing that expectation.

### Identifying Expectations
- A test is based around _EXPECTATIONS_.
- Start identifying AREAS in your code in which you are setting _expectations_.
- By doing this, you know what kind of test you need to run.

```
function add(x, y) {
   return x + y;
}
```
- It would be called like this:
- `add(2,3);  -----// 5`

Expectations about this function:
- When calling the function: 
- __Expectation 1__= `add()function has been defined` and it `exists`.
- __Expectation 2__= the function is accomplishing the `intended task`.
- __Expectation 2__= the function will always be `called as intended`.

### Quiz: Defining Expectations
_ _What Expectations apply to my Function?_
```
function add(x, y) {
   return x + y;
}
```
-[x] Expect 2+3= 5 
-[x] Expect error if non-numbers are used
-[x] Expect 0.2 + 0.2 = 0.3 
- __Answer__: All of these expectations apply to my function! Surprisingly, one of them is actually incorrect at this time - let's see which one that is.

- [StackOverflow: Is JavaScript's Floating Point Math Broken?](https://stackoverflow.com/questions/588004/is-floating-point-math-broken)

- NOTE: the 3rd expectation would be 0.1 + 0.2 = 0.300000...4
- Computers perform Float Math differently.

### Refactoring add()
- How to `refactor a function`, based on the `Identified Expectations`:

- FUNCTION:
```
function add(x, y) {
   return x + y;
}
```
- EXPECTATIONS:
- 1) Expect 2+3= 5
- 2) Expect error
- 3) Expect 0.1 + 0.2= 0.3

- This proces= the "RED-GREEN-Refactor-cycle".

```
function add(x, y) {
   if (typeof x ¬¬ typeof y) 1== ´number´){
    throw new Error(´Params must be a number.´);
   }
   
   return x + y;
}
```
- This function passes expectation 1 & 2.

```
function add(x, y) {
   if (typeof x ¬¬ typeof y) 1== ´number´){
    throw new Error(´Params must be a number.´);
   }
   result 0 x + y;
   if parseInt(result) !==result) {
        result = parseFloat(result.toFixed(1));
   }
   return x + y;
}
```
- This function passes expectation 1,2 & 3
- So this function acts exactly, like before, but this time ERROR free.

### Quiz: Writing Expectations in Code
//Example:
//Expect add(2,3) to equal 5
`expect(add(2,3)).toBe(5);`

//Example:
//Expect add() to throw an error if x/y are not numbers
`expect(add(2, ´test´)).toThrow();`

//Example:
//Expect add(0.1, 0.2) to equal 0.3
`expect(add(0.1, 0.2)).toBe(0.3);`

- Congrats! You just wrote your very first test!

#### Take Away
- Now you 
- 1) understand the importance of testing.
- 2) identify problems with the first version of the add() function.
- 3) refactor your code to solve those issues.
- 4) can be confident not to break anything during refactoring, because the test will always tell you what went wrong.





