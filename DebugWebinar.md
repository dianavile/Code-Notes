# Everything you need to know about _Front End problemsolving and debugging skills_ by Cameron Pittman from [Udacity.com](http://www.Udacity.com)
Check the video [here](https://youtu.be/vftSDWcA6to).

Source: Code Notes thanks to [Thijs Waalders](https://github.com/ThijsWaalders)

## Debugging [Front End] - Tips, Tricks and Advice
A lot of tips can also be used for other development (that's why there are these [brackets].

## Truths of Debugging Any Application
1. **DON'T PANIC**
2. Try to relax
3. Try to focus
4. As found on https://goo.gl/qZr2bE
5. You're a scientist collecting evidence and hypothesizing
6. TEST ONE CHANGE AT A TIME (think control groups) **You only make one change at a time and then you test it before you go too the next change**
7. Simple explanations > complex explanations: Don't think too complicated right away. First you should check all small things like typo's, missing semicolons, brackets on the wrong place, (traling white spaces). Second you should check for bigger issues. Most of the time there is a simple explanation.
8. Examine values and control flow: Is a string really a string? It maybe an array or a number. (there is code to check this out). Also check you control flow (if, else, for, functions, etc.) _because control flow can influence/change values_.
9. Test every assumption and belief: Be 100% sure something is working. Don't assume it is working.
10. Search for key, unique phrases in any errors that pop up - Always search and ask after that for errors _especially unique phrases_.

## Better debugger options:
1. Trying the same thing over and over again, if you run code and you get a result, if you run the exect same code without any changes, you won't get any other results (normally). Don't run you code again if it works, try to learn why it works (or doesn't). _Go through the steps above_.
2. When testing control flow and I don't have the option for a good debugger, just keep it super simple, throw 1 `console.log` and move it to the next (_Don't keep it there_).
3. In any JavaScript code you can throw the word debugger so it will pauze/executing (in dev tools) that code on that line and you'll be given the sources panel/tab Wich will let you inspect the variables and call stack at that point (this way you can learn better how and why).
4. Use VScode + extensions! They are the best way for easy fast and simple workflow.
5. When you're totally stuck.. ([at +/-22 min](https://www.youtube.com/watch?v=vftSDWcA6to&feature=youtu.be))
    - Take a break! Sleep on it!
    - Talk it out. In detail, explain to someone why the bug might be X or why it couldn't possibly be Y.
    - Work forwards and backwards - ensure the control flow before and after where your bug might be is working correctly.
    - If you really don't know where the bug lives, maybe delete large swaths of code or maybe files (one at a time!) or run the code.
6.  - Remember, this is a learning experience. Get excited! You're about to learn something new!
    - Make the bug worthwhile - learn from the mistake you or someone else has made and take action to make sure this same bug doesn't occur again the next time.


## Extra tips from live questions:
1. Tips for debugging other peoples codes:
    - Code that you write a while ago and forgotten about is a also someone elses code.
    - CTRL + F a ```function``` (in VScode) to search for that function to find it somewhere else or find the definition.
2. Don't comment a lot, only if it is really nessecarely. (So don't if this is that and if that is this then do that..)
3. How should I write unit tests for my code?
    - Unit tests: (and this an awnser for a lot of questions) **_"There is no wrong or right approach, there are a lot of different mindsets."_** Any kind of unit test is better then no unit test. Don't wait until you need to test!
    The trick there _**if you wan't to make your life easier then setting up your test is the first thing you should do when you start a project!**_


    ended at 30 minutes https://www.youtube.com/watch?v=vftSDWcA6to&feature=youtu.beg