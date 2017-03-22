### [Andrew Clark](https://github.com/acdlite) talk on React Fiber. [Link](https://www.youtube.com/watch?v=aV1271hd9ew)

* His notes on React Fiber. [Here](https://github.com/acdlite/react-fiber-architecture)
* This talk, happened in ReactNext 2016, introduces what React Fiber (A core reimplementation for React) stands for
* Talks about how the current React scheduling (for re-renders and stuff) is a pull based, completely synchronous execution for applying an update
* And the need for priority scheduling, preferential updates, pause current execution and resume later on is being drawn.
* Javascript is single threaded. Pause and resuming a stack is not very common. `debugger` statement does that.
* [Concurrency](https://en.wikipedia.org/wiki/Concurrency_(computer_science)) can be achieved in Javascript with [Generators](https://developer.mozilla.org/en/docs/Web/JavaScript/Guide/Iterators_and_Generators)
* A very practical use case for react fiber is if you have to choose between an animation re-render and a data update. You would want the animation re-render to finish immediately.
* Fibre is a single unit of concurrency, and having a bunch of fibers (where each fiber represents render for one component)
* The current react works in a manner that each component is a functionn of data `v = f(d)`, but it's just a function which cant be paused/resumed. With fiber, it will have that capability
* `requestIdleCallback(cb)` is a browser provided function which will invoke the callback in the browser's idle time, with this we can achieve the pause n resume. So basically lower priority fibers (renders) are called using this, so that it can look for higher priority work registered with another callback `requestAnimationFrame(cb)`
* Can help implement return multiple elements from a component. (Currently we have to wrap it in a `div` or a `span`

### [Jay Phelps](https://twitter.com/_jayphelps) talk on RxJS usage for asynchronous side-effects for Redux. [Link](https://www.youtube.com/watch?v=AslncyG8whg)

* So this talk is focussed on how to efficiently focus on async integration with redux.
* Some other side reading on this. [Link 1](https://medium.com/@benlesh/redux-observable-ec0b00d2eb52#.6ezw5m48i)
* They have created a node package to achieve what I am about to write below - [redux-observables](https://www.npmjs.com/package/redux-observable)
* This is a redux middleware
* Stuff that this will allow you to do
    - Introduce a time delay
    - Debounce for whatever time
    - Cancel an AJAX call (Server side searching calls to show an auto complete for search text)
    - Multiplexed Web sockets
