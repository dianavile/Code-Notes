# JavaScript DOM- [DOM](#2.19-DOM)
__Source:__ _Accesibility - Udacity Front End Web Development Nanodegree_
__Created with__ [@ArtNerdnet](https://github.com/artnerdnet)

#### Goals:
- What is the Document Object Model (DOM)?
- How the DOM gets created? 
- How to access the DOM with JavaScript?

### Table Of Contents
- __The DOM__ 
- __Create the DOM__ 
- __Access the DOM__ 

### THE DOM: What is the Document Object Model (DOM)?
- The __DOM__= `"Document Object Model"` 
- It is _`provided by the browser`_
- It is a __tree-like structure__ _`representation of the HTML document`_. 
- It contains all __nodes__ `relationship between elements`,  (=the element `content` and `properties`).

- :exclamation: __NOTE:__  The DOM is __NOT__ _part of the JavaScript language_.
- It __ONLY__ references the _document object model in one place_, in its "Global Object" section:
- __ECMAScript__ is the language specification JavaScript is based on. 

### Create the DOM: How the DOM gets created? 
- When you request a website, it responds with HTML: 
- These bytes recieved are run through a `parsing process` 
- ===> it determine characters (eg., start tag character, atribute) 
- ===> it is a tokenizer 
- ===> it shows its tokens (DOCTYPE, start tag, end tag, comments) 
- ===> it convert into the DOM (a tree structure, that captures HTML content and properties and relationships between the nodes)

So to reiterate the process, it's:
- `characters`
- `tags`
- `tokens`
- `nodes`
- `DOM`

### Access the DOM: How to access the DOM with JavaScript?
_ There are various ways to access the DOM with JavaScript:

1) SELECT AN ELEMENT BY ID
```
document.getElementById();
```
If we ran the code above in the console, we wouldn't get anything, because we did not tell it the ID of any element to get! We need to pass a string to .getElementById() of the ID of the element that we want it to find and subsequently return to us:
``` 
document.getElementById('footer');
```

2) SELECT MULTIPLE ELEMENTS 
The next two DOM methods that we'll be looking at that both return multiple elements are:
`.getElementsByClassName()`
`.getElementsByTagName()`

Accessing Elements By Their Tag
After looking at both .getElementById() and .getElementsByClassName(), the new .getElementsByTagName() method should seem quite easy on the eyes:

```
document.getElementsByTagName('p');
```
__Important things to keep in mind:__
1) both methods use the `document object`
2) both `return multiple items`
3) the __returned list__=`__NOT__ an array[]`

__Node__
A Node acts like a blueprint containing all the data (properties) and the functionality (methods). This is called an interface. Based on the interface we know the properties and methods that are going to be applied to the individual items, which we call nodes.

__ELEMENT INTERFACE__
The element interface inherits all properties AND methods from the Node. It is a descendent iself of the node, as well as its elements.

Example:


#### Resources
- [JavaScript Closure, SetOutTime, Scopes](https://medium.com/coderbyte/a-tricky-javascript-interview-question-asked-by-google-and-amazon-48d212890703)

#### Take Away
- The DOM is: `document object modal`, constructed __from the browser__ 
- globally accessible by JavaScript code using the `document object`

Creating Content with JavaScript
Working with Browser Events
Performance


