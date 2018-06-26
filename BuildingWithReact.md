# Building with React

## 1. Why React?
Why `React` is so popular at the moment?

- 1) __Composition__: it combines easy functions to create complex functions.

- 2) __Declarative__ (Not imperative): you tell JS what you want to do. 
It takes care of the steps itself, without you worrying about it.

- 3) __Unidirectional data flow__
The data flows through a component in one direction only (Not 2 way data binding).
=> from parent to children 
__NOTE:__ the data update ONLY occurs in parent component.

- 4) React is __just JavaScript__.

### Virtual DOM 
The `Virtual DOM`=  a tree in which each node is an HTML element. 
- React is able to traverse and carry out operations on this Virtual DOM, 
- saving our app from having "costly" activity on the actual DOM.
[Virtual DOM](https://reactjs.org/docs/optimizing-performance.html#avoid-reconciliation) 

### Diffing Algorithm
`Diffing`= to make efficient changes to the DOM. 
- With diffing, old DOM nodes are taken out and replaced only when necessary. 
- This way, our app doesn't perform any unnecessary operations to figure out when to render content.
[Diffing Algorithm](https://reactjs.org/docs/reconciliation.html#the-diffing-algorithm)

## 2. React Rendering
Normally, when you code, the render process will both 
"Decide what data to render" &  "Render the data" at the same time.

In React this process is decoupled:
Render component onto root div
ReactDOM takes 2 arguments:

- 1) What data to render (=React component)
- 2) Where to render the data (=DOM element)
NOTE: ReactDom is used, because we work in the browser.

This makes it possible to RENDER on:
  - native devices.
  - server.
  - VR environments.

## CREATE A REACT COMPONENT
EXAMPLE - index.html
```

<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8" />
    <title>Add React in One Minute</title>
  </head>
  <body>

    <h2>Add React in One Minute</h2>
    <p>This page demonstrates using React with no build tooling.</p>
    <p>React is loaded as a script tag.</p>

    <!-- We will put our React component inside this div. -->
    <div id="like_button_container"></div>

    <!-- Load React. -->
    <!-- Note: when deploying, replace "development.js" with "production.min.js". -->
    <script src="https://unpkg.com/react@16/umd/react.development.js" crossorigin></script>
    <script src="https://unpkg.com/react-dom@16/umd/react-dom.development.js" crossorigin></script>

    <!-- Load our React component. -->
    <script src="like_button.js"></script>

  </body>
</html>

```
EXAMPLE - like_button.js
```
'use strict';

const e = React.createElement;

class LikeButton extends React.Component {
  constructor(props) {
    super(props);
    this.state = { liked: false };
  }

  render() {
    if (this.state.liked) {
      return 'You liked this.';
    }

    return e(
      'button',
      { onClick: () => this.setState({ liked: true }) },
      'Like'
    );
  }
}

const domContainer = document.querySelector('#like_button_container');
ReactDOM.render(e(LikeButton), domContainer);
```

## RESOURCES: Install React
There are three ways to install REACT:
1) REACT COMPONENT (see above)
[REACT COMPONENTS-Add React to a website](https://reactjs.org/docs/add-react-to-a-website.html#try-react)
2) REACT WITH JSX (BABEL NEEDED)
[New App](https://reactjs.org/docs/add-react-to-a-new-app.html)
[Existing App](https://reactjs.org/docs/add-react-to-an-existing-app.html)
3) REACT WITHOUT JSX (__NO__BABEL NEEDED)
[REACT withouth jsx](https://reactjs.org/docs/react-without-jsx.html)
[REACT cdn links](https://reactjs.org/docs/cdn-links.html)



