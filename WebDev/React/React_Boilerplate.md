# Understanding stuff behind [React-Boilerplate](https://github.com/react-boilerplate/react-boilerplate). (Mind = blown)

### React

### Redux

### ImmutableJS

### React-Router

### Reselect

### React-intl

### [Jest](https://facebook.github.io/jest/) and [Enzyme](http://airbnb.io/enzyme/)

* To be explored

### [Sanitize.css](https://github.com/jonathantneal/sanitize.css)

* Fixes cross browser CSS defaults anomalies to some extent (Cuz I haven't seen it in works)

### [Redux-Saga](https://github.com/redux-saga/redux-saga)

* This is a package to manage stuff like async API calls easily.
* And it has APIs to batch calls (Reject new calls if current call is pending). Using `takeLatest` effect
* Also allows accessing browser cache? (Not explored)
* Have to explore a lot more

### [ES6 Generators](http://2ality.com/2015/03/es6-generators.html)

* These are the functions which can be paused and resumed!!!
* Created using `function*` syntax which creates a generator
* The definition creates a generator, which should be instantiated to get a function that can be paused and resumed
* Pausing is by writing a `yield` statement. Resuming is by calling `next()` on the created function instance
* Checkout examples in the link above
* You can implement an observable with this!!!

```javascript
function* myObservableGenerator(subscriptions) {
  console.log("Started the observer");
  yield;
  while(yield !== "somegibberishhere")
    subscriptions(yield);
  return;
}

let observable1 = new myObservableGenerator();
observable1.next(); //this creates and starts the observable

function changeVal(newval) {
  observable1.next(newVal);
}

function stopObservable() {
  observable1.next("somegibberishhere");
}
```

### [Styled-Components](https://github.com/styled-components/styled-components) (Other major Mind = Blown moment)

* You can create your own copy of the HTML component with your default styling applied
* You can add css pseudo selectors like `hover` and `active` for those elems
* You can control CSS values via the props. (OMG!!)
* Check this example out

```JSX
import styled from 'styled-components';

const Button = styled.button`
  /* Adapt the colors based on primary prop */
  background: ${props => props.primary ? 'palevioletred' : 'white'};
  color: ${props => props.primary ? 'white' : 'palevioletred'};

  font-size: 1em;
  margin: 1em;
  padding: 0.25em 1em;
  border: 2px solid palevioletred;
  border-radius: 3px;
  
  &:hover {
    box-shadow: inset 1px 1px 2px rgba(0,0,0,0.1);
  }
`;

export default Button;
```

### [react-router-redux](https://github.com/reactjs/react-router-redux)

* This small package keeps the react-router's data (Read URL) into the redux state, so that when you replay the user activity using live reload, it can also play back page navigations now.
* It is now being made as a part of the [React-Router](https://github.com/ReactTraining/react-router) itself

### TO come
