## Writing Test Suites (Lesson 22)

#### Correctiong our Asynchronous Test

- _[OPTIONAL]_If you are curious to see what happens in each combination of passing in vs. calling done, one of our students tried all of them to see what would happen. The results in this [thread](https://discussions.udacity.com/t/async-tests-why-the-second-done-call/40751/6?u=durant) are illuminating and go beyond the [demos for Jasmine 2.1.2.](https://jasmine.github.io/2.1/introduction.html).

- Take special note of the case where if you pass in the done function as an argument, you must call it (=otherwise things break!). 
- The Jasmine team might accept a pull request to update [this information](https://discussions.udacity.com/t/async-tests-why-the-second-done-call/40751/4) for all students.
- If you _test async_, you do NO NEED to pass in and call `done`.
