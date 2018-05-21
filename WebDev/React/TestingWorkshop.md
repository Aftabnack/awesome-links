# Intro

* This is my notes from KCD's testing course on FrontendMasters which was free for some duration. Kudos to them!!
* Repo to use: [https://github.com/kentcdodds/testing-workshop](https://github.com/kentcdodds/testing-workshop)

## Types of testing

* Static Code Analysis - ESLint (without style specific rules) & FlowType - Easy to setup, good ROI
* Unit testing(Jest) - Testing Individual components without having to worry about external deps
* Integration testing(Jest) - Testing many components working together
* End to end tests(Cypress)- Treating app as a blackbox and testing it from user perspective

**General structure of the test**

```javascript
test('title', () => {
  //arrange
  
  //act
  
  //assert
})
```

## Unit tests

* Using `textContent` instead of `innerHTML` will not care whether you wrap text in any number of elems
* Using `toMatch` instead of `toEqual` when you start writing tests and then change it to make it more specific when necessary.
* Do not use any library that encourages you to write test cases in a manner in which you would have to unnecessarily make changes to your source code. `Shallow` from enzyme is an example.
* Very tightly coupled test cases where `Shallow` are used is not good, since even minor meaningful refactor of the code needs us to change the test cases which are worthless
* It is okay to not write perfectly isolated unit test cases
* What you should be testing is the behaviour/expected change and not the implementation detail.
