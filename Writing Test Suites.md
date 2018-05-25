## Writing Test Suites (Lesson 22)

####Correctiong our Asynchronous Test

- _[OPTIONAL]_If you are curious to see what happens in each combination of passing in vs. calling done, one of our students tried all of them to see what would happen. The results in this thread are illuminating and go beyond the demos for Jasmine 2.1.2. 
- Take special note of the case where if you pass in the done function as an argument, you must also call it (otherwise things break!). 
- And hopefully the Jasmine team will accept a pull request to update this information for all students (see thread if curious).
- Also note, if you are testing async, you do not need to pass in and call done.