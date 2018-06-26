# React- summary
This summary is made from LessonMaterial from @Nicolas Marcora.

`React`= a `JavaScript library for creating user interfaces. 
Its core principles are declarative code, efficiency, and flexibility.`

## Intro: The power of React

1) Define things ONLY once
2) Work with your data
3) React does the rest: everything else falls into place without you having to worry about it. 
4) It is fast!

## React Syntax:

TO RENDER
```
ReactDOM.render(
  <App />,
  document.querySelector('#root')
)
```
### Styling
Just like with regular HTML, we can give our React elements attributes. For example, you easily target your element with CSS by giving it a class or an id attribute.

__NOTE__: Since the class keyword is already taken in JavaScript, className is used instead.
Also note: Attributes in React are camelCased. i.e. onClick instead of onlick.
```
const App = () => <h1 className='title' id='hello'>Hello</h1>;
```

### Interpolation
Since we're not actually using HTML, but JSX, we have the power to use JavaScript directly inside our components. All you have to do wrap your JavaScript code around {}.
```
const App = () => <h1>{3 + 5}</h1>;
const App = () => <h1>{'hello'.toUpperCase()}</h1>;
const name = 'Diana';

const App = () => <h1>{name}</h1>;
const name = 'Diana';

const App = () => <h1>{name.length > 4 && name}</h1>;
const name = 'Diana';

const App = () =>
  <h1>{name.length > 4 ? name : 'Your name is too short.'}</h1>;
```
  
### Props
Every React component gets passed a props object. 
This object has all data passed to a component 
and is how a parent component can send things to a child component.
Since props are not directly owned by a component, you should avoid modifying them.

```
const App = props => <h1>{`Hello, ${props.name}!`}</h1>;

ReactDOM.render(
  <App name='Diana' />,
  document.querySelector('#root')
)
Composition
You can render React components within other React components.

const Title = () => 'Hello';

const App = () => (
  <div>
    <Title />
  </div>
);
```

### Class components
Sometimes just having props and rendering elements is not enough. 
Class components allow you to more logic (lifecycle methods) and state.

```
class App extends React.Component {
  render() {
    return <div>App</div>;
  }
}
State
Sometimes, just having data passed down by a parent component is not enough, and we need the component to have some data of its own. This is called a component's state.

class App extends React.Component {
  state = {
    name: 'Diana'
  }

  render() {
    return <div>{this.state.name}</div>;
  }
}
```
or
```
class App extends React.Component {
  constructor() {
    this.state = state = {
      name: 'Diana'
    }
  }

  render() {
    return <div>{this.state.name}</div>;
  }
}
```

### Modifying state
We said before that props don't belong to a component, so we should avoid modifying them. But state totally belongs to a component, so it's perfectly ok to change it. However, you should never change it directly. 
Instead, class components give you a handy method called setState.
```
class App extends React.Component {
  state = {
    name: 'Diana'
  }

  capitalizeName = () => {

    this.state.name = this.state.name.toUpperCase(); // AVOID THIS
    this.setState({name: this.state.name.toUpperCase()}); // DO THIS INSTEAD

  }

  render() {
    return <div>

      {this.state.name}

    </div>;
  }
}
```

### Events
Like in regular HTML, you can add events to your React elements. 
This allows you to "react" to things like a button click or a form submission.
The list is long, but you can learn more about what events are available here.
```
class App extends React.Component {

  // ...

  render() {
    return <div>

      {this.state.name}
      <button onClick={this.capitalizeName}>CAPITALIZE</button>
    </div>;
  }
}
```

### Resources
[React](https://s3.eu-west-2.amazonaws.com/nmarcora/react-from-scratch.html)
