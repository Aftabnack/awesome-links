# Understanding stuff behind [React-Boilerplate](https://github.com/react-boilerplate/react-boilerplate). (Mind = blown)

### [React](https://facebook.github.io/react/)

* Needs no explaination
* Only framework as of now and to my knowledge which has a pull based update mechanism
* The biggest killer framework yet!

### [Redux](http://redux.js.org/)

* Data management (Model in MVC) simplified
* Single state tree for your entire application
* Three simple principles
  * Single source of truth
  * State is read-only
  * State modification is done via pure functions
* Simple APIs to interact with them [API reference](https://github.com/reactjs/redux/blob/master/docs/api/README.md)
* Actions (created by actionCreators) describe the change to be made
* Reducers are where changes are made
* Store is where everything comes together

### [ImmutableJS](https://facebook.github.io/immutable-js/)

* Library that helps in achieving the pure modifications required in Redux
* Has hell lot of APIs for ease of object[Map]/array[List] manipulations
* Recommended for most usecases and is optimized for good perf!

> Note: There is one scenario in which this has failed me
> * If my parent has Data A and Data B passed to it (from same reducer)
> * If ChildA is getting Data A & ChildB is getting Data B from the parent
> * If I try to update Data A and expect only ChildA to re-render, doesn't work since Immutable would have changed reference of everything, ChildB would also re-render even with `PureComponent` used


### [React-Router](https://github.com/ReactTraining/react-router)

* Client side routing between pages
* Maintain common layout between pages/views
* Easy to setup and use
* Using import plugin in the routes will make sure only that route's assets are downloaded onto the browser

### [offline-plugin](https://github.com/NekR/offline-plugin)

* Webpack plugin which will cache your application assets for offline loading of assets
* Uses serviceWorker and AppCache to achieve this
* We need clientside runtime and webpack config plugin for this to work
* This is to just save the assets, the actual application to work cleanly offline, should probably use some CouchDB (indexedDB implementation) to save to local when no network

### [ESLint](http://eslint.org/)

* Easy linting utility to check the semantics of your code
* Can throw error/warning on some pre-defined standards
* Complete list can be seen [here](http://eslint.org/docs/rules/)
* Creating a ESLint rule is also [simple](ESLint_Custom.md).

### [Webpack](https://webpack.js.org/)

* Swiss Army Knife for the front-end development
* Boon for developing SPA
* Combine your code, bundle, minify, uglify, [strip unused exports](https://webpack.js.org/guides/tree-shaking/) before serving it to client
* Provides provisioning for Hot Reloading
* Understand the concepts [here](https://webpack.js.org/concepts/)
* Get to the documentation [here](https://webpack.js.org/configuration/)

### [Reselect](https://github.com/reactjs/reselect)

* Save lot of computation by memoizing the function results
* What it does is, it takes functions called `selectors` to derive the param value to the function
* Until and unless the param value changes it won't re-run the function and instead returns the previous cached result
* It caches only one previous return value of a function
* The `selectors` are composable btw

### [React-intl](https://github.com/yahoo/react-intl)

* This will take care of re-formatting date, numbers and such according to the locale
* This is for i8ln

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

> Styled Components universal components [Here](https://medium.com/styled-components/announcing-primitives-support-for-truly-universal-component-systems-5772c7d14bc7)

### [react-router-redux](https://github.com/reactjs/react-router-redux)

* This small package keeps the react-router's data (Read URL) into the redux state, so that when you replay the user activity using live reload, it can also play back page navigations now.
* It is now being made as a part of the [React-Router](https://github.com/ReactTraining/react-router) itself
