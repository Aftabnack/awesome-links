## Suggested migration path for react codebase

* You can look at the high level changelogs [here](https://github.com/facebook/react/blob/master/CHANGELOG.md).
* You may probably have one of the blog posts listed [here](https://facebook.github.io/react/blog/all.html) that will give little bit more detailed explaination on this.
* To help with migration of the code, react provides you with predefined "codemods" which will traverse through your code and do the migration. Check out the project [here](https://github.com/reactjs/react-codemod)
* They use [this](https://github.com/facebook/jscodeshift) AST based "codemod runner" to effect the migration, we can use this for something similar if we are trying it out.. :P
