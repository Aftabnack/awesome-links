## React revisited

**Lot of things have changed since I started to learn React, so I wanted to go over some basic concepts, and write things I found interesting/new**

* In rest-spread syntax, if same keys are encountered, the last value of the key will override everything before it
* `ref` can take a function which will give you access to DOMNode/component's this, which you can save in a variable on this!
* You can declare class properties which can hold stuff like `state` - And this initialization happens after `constructor` is called, so you will also have `this.props` available to you

#### Bibliography

* [React basics course by Kent.C.Dodds](https://egghead.io/courses/the-beginner-s-guide-to-reactjs)
* [Advanced React Course by Kent.C.Dodds](https://egghead.io/courses/advanced-react-component-patterns)
