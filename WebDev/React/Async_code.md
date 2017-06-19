# Call libraries

### [Axios](https://github.com/mzabriskie/axios)

* Built to work on both Web (XMLHttpRequest) and node (HTTP/HTTPS)
* Promise based API. Keep chaining the thens..:P
* Auto resolves all the responses (`response.json().then()`)
* Resolves response with error status into reject/catch block
* Provides you a way in which you can maintiain defaults across requests globally/instance-specfic which can be overridden when making the call
* Provides request/response interceptors to do what you want before making a request/as soon as you get the response.
* Only two dependancies on the package.

### [Request](https://github.com/request/request)

* This is a worthy challenger to Axios.
* Won't go into much details on it

# React-redux Async

* There are different things that you want to achieve when used in conjunction with UI code.
* Stuff like debouncing, timeout, cancelling requests are needed
* Async code in 4 different ways with code. [Link](https://medium.com/react-native-training/redux-4-ways-95a130da0cdc)
* Comparison between Redux Saga and Redux Observables. [Link](https://hackmd.io/s/H1xLHUQ8e)

### Redux-Saga

* Function generators based
* This is a redux middleware
* Watcher + Worker model
* Tell Program HOW to do things
* Take time to reason about code
* Time required to learn to write this is less compared to observables.

### [Redux Observables](https://github.com/redux-observable/redux-observable)

> [Jay Phelps](https://twitter.com/_jayphelps) talk on RxJS usage for asynchronous side-effects for Redux. [Link](https://www.youtube.com/watch?v=AslncyG8whg)

* So this talk is focussed on how to efficiently focus on async integration with redux.
* Some other side reading on this. [Link 1](https://medium.com/@benlesh/redux-observable-ec0b00d2eb52#.6ezw5m48i)
* They have created a node package to achieve what I am about to write below - [redux-observables](https://www.npmjs.com/package/redux-observable)
* Complete [reference](https://redux-observable.js.org/)

> Features

* Completely based on reactive programming paradigm [RxJS](https://github.com/ReactiveX/RxJS) and Observables
* Using this needs a sound understanding of RxJS & Observables which will take time to get used to
* This is a redux middleware
* `Epic` based: Type + Operations
* Tell Program WHAT things to do
* Easy to reason about code
* Highly reusable code
* Stuff that this will allow you to do
    - Introduce a time delay
    - Debounce for whatever time
    - Cancel an AJAX call (Server side searching calls to show an auto complete for search text)
    - Multiplexed Web sockets
