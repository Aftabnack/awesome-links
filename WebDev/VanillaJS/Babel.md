## [Babel](https://github.com/babel/babel)

* Write tomorrow's javascript today!!
* Transpiles the latest code back to ES5 so that it works on all the browsers.
* You can target specific versions of node/browsers using [`env` preset](https://github.com/babel/babel/tree/master/packages/babel-preset-env)
* Try babel online [here](https://babeljs.io/repl)

---

* [User Handbook](https://github.com/thejameskyle/babel-handbook/blob/master/translations/en/user-handbook.md)
* [Core APIs](https://babeljs.io/docs/core-packages/)
* [Usage for transpiling files](https://babeljs.io/docs/usage/cli/) to work in browser env for example
* [Usage in Node](https://babeljs.io/docs/usage/babel-register/) for transpiling on the fly without coverting and deploying the converted code

---

#### Writing Custom Babel plugin

* [Complete guide](https://github.com/thejameskyle/babel-handbook/blob/master/translations/en/plugin-handbook.md)
* [Example on Sitepoint](https://www.sitepoint.com/understanding-asts-building-babel-plugin/)
* [Understand babel's AST](https://astexplorer.net/), it uses [babylon parser](https://github.com/babel/babel/tree/master/packages/babylon) by default
* [Understand the babel type helpers](https://github.com/babel/babel/tree/master/packages/babel-types)
