# Amazing packages in React ecosystem

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

* [Documentation](https://reacttraining.com/react-router/)
* Client side routing between pages
* Maintain common layout between pages/views
* Easy to setup and use
* Using import plugin in the routes will make sure only that route's assets are downloaded onto the browser

### [Reselect](https://github.com/reactjs/reselect)

* Save lot of computation by memoizing the function results
* What it does is, it takes functions called `selectors` to derive the param value to the function
* Until and unless the param value changes it won't re-run the function and instead returns the previous cached result
* It caches only one previous return value of a function
* The `selectors` are composable btw

### [React-intl](https://github.com/yahoo/react-intl)

* This will take care of re-formatting date, numbers and such according to the locale
* This is for i8ln

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

### [GraphQL](http://graphql.org/)

* New spec for creating backend services
* Exposes one endpoint from the entire server
* That endpoint expects the user to describe what he is looking for; Then it will respond with that data provided he has access to it.
* Switch to [GraphQL](http://graphql.org/graphql-js/) [[Github](https://github.com/graphql/graphql-js)]. Easier and structured data endpoints.!!
  * [Apollo](http://dev.apollodata.com/) is a client to make it easier to work with GraphQL
  * One [example](https://dev-blog.apollodata.com/reducing-our-redux-code-with-react-apollo-5091b9de9c2a) of what the impact of migration would be.
  
  ---
  
  * [Guide to GraphQL](https://css-tricks.com/front-end-developers-guide-graphql/)
  * [Apollo Client - future of state management](https://dev-blog.apollodata.com/the-future-of-state-management-dd410864cae2)
