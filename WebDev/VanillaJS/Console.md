## Cool stuff that you can do with your console!

* It has 4 most widely used methods - `log` `warn` `error` `info`
* `error` prints with the stack trace too!!
* It can do substitutions!!

```javascript
console.log('string %s', 'substitutions')
console.log('this is an object %o', { obj: { obj2: 'hello' }}) //%O also means the same
console.log('int: %d, floating-point: %f', 1, 1.5) //%d & %i can be used interchangeably
```


* You can apply CSS when printing message!!

```javascript
const success = [
 'background: green',
 'color: white',
 'display: block',
 'text-align: center'
].join(';');
const failure = [
 'background: red',
 'color: white',
 'display: block',
 'text-align: center'
].join(';');
console.info('%c /dancing/bears was Successful!', success);
console.log({data: {
 name: 'Bob',
 age: 'unknown'
}}); // "mocked" data response
console.error('%c /dancing/bats failed!', failure);
console.log('/dancing/bats Does not exist');
```

* There are other cool APIs
  * `assert` - takes two arguments , if the first argument evaluates to a falsy value, then it displays the second argument
  * `table` - The table method displays an array or object as a table
  * `group` - Groups stuff together and indents on the console
  *
  
```javascript
//Group usage
console.group();
console.log('I will output');
console.group();
console.log('more indents')
console.groupEnd();
console.log('ohh look a bear');
console.groupEnd();

//Time usage
console.time('test');
...
console.timeEnd('test');
```



> Source: https://medium.freecodecamp.org/how-to-get-the-most-out-of-the-javascript-console-b57ca9db3e6d

> Console MDN: https://developer.mozilla.org/en/docs/Web/API/console

> Console spec: https://console.spec.whatwg.org/
