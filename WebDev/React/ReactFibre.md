### Andrew Clark's (@acdlite) talk on React Fiber. [Link](https://www.youtube.com/watch?v=aV1271hd9ew)

* This talk, happened in ReactNext 2016, introduces what React Fiber (A core reimplementation for React) stands for
* Talks about how the current React scheduling (for re-renders and stuff) is a pull based, completely synchronous execution for applying an update
* And the need for priority scheduling, preferential updates, pause current execution and resume later on is being drawn.
* Javascript is single threaded. Pause and resuming a stack is not very common. `debugger` statement does that.
* [Concurrency](https://en.wikipedia.org/wiki/Concurrency_(computer_science)) can be achieved in Javascript with [Generators](https://developer.mozilla.org/en/docs/Web/JavaScript/Guide/Iterators_and_Generators)
* A very practical use case for react fiber is if you have to choose between an animation re-render and a data update. You would want the animation re-render to finish immediately.
* Fibre is a single unit of concurrency
