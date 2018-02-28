**This page will contains links on how to focus on the perf of a react app**

* [React docs on Perf](https://facebook.github.io/react/docs/perf.html)  [[usage](https://engineering.musefind.com/how-to-benchmark-react-components-the-quick-and-dirty-guide-f595baf1014c)]
* [React performance timeline](https://facebook.github.io/react/blog/2016/11/16/react-v15.4.0.html#profiling-components-with-chrome-timeline)
* [Why did you update](https://github.com/garbles/why-did-you-update)
* [Explore the size of the created bundle](https://www.npmjs.com/package/source-map-explorer)
* Consider initial server side rendering!
* [Have to do tree shaking!](https://webpack.js.org/guides/tree-shaking/)
* Use `React.PureComponent` or write your own `shouldComponentUpdate`

---

## Improving the performance in react app

* All the inline-functions, functions used with bind, variable defaults like ` x || []`, functions whose return value is directly sent as props will create new reference, hence `shouldComponentUpdate` will always return true.
* To solve this, you can declare them as consts (For the 1st 3 cases), use [`reselect`](https://github.com/reactjs/reselect) which memoises the previous inputs and caches the result for it (For the last case).

* [Detailed Article](https://medium.com/@esamatti/react-js-pure-render-performance-anti-pattern-fb88c101332f)

---

* [Javascript Startup breakdown](https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/javascript-startup-optimization/)
* [Improving dragging react performance](https://medium.com/@alexandereardon/dragging-react-performance-forward-688b30d40a33)
* [Perf tuning a React App](https://codeburst.io/performance-tuning-a-react-application-f480f46dc1a2)
* [Cost of JS](https://medium.com/dev-channel/the-cost-of-javascript-84009f51e99e)
* [Critical Request](https://css-tricks.com/the-critical-request/)
* [A tinder PWA case study](https://medium.com/@addyosmani/a-tinder-progressive-web-app-performance-case-study-78919d98ece0)

---

> The below two links are obsolete, since `react-addons-perf` don't work with React 16

* [Improve perf part 1](http://benchling.engineering/performance-engineering-with-react/)
* [Improve perf part 2](http://benchling.engineering/deep-dive-react-perf-debugging/)
