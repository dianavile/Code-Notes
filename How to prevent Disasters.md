## TEST: How to Prevent Disasters(Lesson 18)

### Description
- How to use tooling as a safety net for your code.
- Use it automatically to check the code you write
- And automatically run tests.


### Linting
- _LINTING_ = `a way to automatically check JavaScript code for errors.`
- This can be done via your:
- 1) editor (live linting)
- 2) build process
- 3) pre-commit hook in version control

There is a difference of `CodeStyle Linting` vs `Syntax Linting`.
- 1) __Syntax (Structural) Linting__= checks for `JavaScript Anti-patterns`, like: `unreachble statements` and forget a `strict comparison against null`.
- 2) __Code Style Linting__ = to know errors regarding
- incorrect camel cases of `variables 
- particular incorrect `braces {}[] for functions.

__NOTE:__ The linting ONLY checks for intentional errors. 
- YET, it doesn´t have any idea of what you are trying to accomplish with your code.

- A linter helps your code to:
- 1) uncover code style problems
- 2) help eliminate dead code or variables

### Popular JavaScript Linters
- 1) [JSHINT](http://jshint.com/)
- 2) [JSCS](https://www.npmjs.com/package/jscs)
- 3) [ESLint](https://eslint.org/)

### Unit Test
- Use `Unit Test` to test the __functionality of your project.__
- To test the Front-End code in the browser.


#### Resources
- [Comparison of JavaScript linting tools](sitepoint.com/comparison-javascript-linting-tools/)
- [ESLint](https://eslint.org/)
- [Sublime Linter](http://www.sublimelinter.com/en/latest/)
- [gulp-eslint on npm](https://www.npmjs.com/package/gulp-eslint)
- [How to Use Git and Github course](https://eu.udacity.com/course/how-to-use-git-and-github--ud775)
- [Udacity JavaScript Testing course](https://eu.udacity.com/course/javascript-testing--ud549)
- [PhantomJS gulp plugin on npm](https://www.npmjs.com/package/gulp-jasmine-phantom)
- [Jasmin Documentation](https://jasmine.github.io/)


