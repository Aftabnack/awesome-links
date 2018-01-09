## React revisited

**Lot of things have changed since I started to learn React, so I wanted to go over some basic concepts, and write things I found interesting/new**

* In rest-spread syntax, if same keys are encountered, the last value of the key will override everything before it
* `ref` can take a function which will give you access to DOMNode/component's this, which you can save in a variable on this!
* You can declare class properties which can hold stuff like `state` - And this initialization happens after `constructor` is called, so you will also have `this.props` available to you

**Props vs State is a common argument in React world**

* [Uber's guide](https://github.com/uberVU/react-guide/blob/master/props-vs-state.md)
* http://lucybain.com/blog/2016/react-state-vs-pros/

**Transitions in React**

* [Fade transition component](https://codesandbox.io/embed/y26rj99yov?codemirror=1)

#### Bibliography

* [React basics course by Kent.C.Dodds](https://egghead.io/courses/the-beginner-s-guide-to-reactjs)
* [Advanced React Course by Kent.C.Dodds](https://egghead.io/courses/advanced-react-component-patterns)
* [Advanced React Concepts](https://engineering.opsgenie.com/you-learned-the-basics-of-react-now-what-389e69be3c5a)
* [8 key decisions for a React project](https://medium.freecodecamp.org/8-key-react-component-decisions-cc965db11594)
