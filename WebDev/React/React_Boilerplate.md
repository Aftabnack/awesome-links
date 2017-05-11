# Understanding stuff behind [React-Boilerplate](https://github.com/react-boilerplate/react-boilerplate). (Mind = blown)

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
```
