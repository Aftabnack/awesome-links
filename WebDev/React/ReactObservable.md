
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
