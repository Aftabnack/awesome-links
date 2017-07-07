## `Async` and `Await` syntax and why you should use it

* You can convert your asynchronous codes with callback trees into one simple same level code
* Boosts the code readability and understandability by a lot.

**Before**
```javascript
function executeAsyncTask () {  
  return functionA()
    .then((valueA) => {
      return functionB(valueA)
        .then((valueB) => {          
          return functionC(valueA, valueB)
        })
    })
}
```

**After**
```javascript
async function executeAsyncTask () {  
  const valueA = await functionA()
  const valueB = await functionB(valueA)
  return function3(valueA, valueB)
}
```

**Multiple parallel requests with `async/await`**

```javascript
async function executeParallelAsyncTasks () {  
  const [ valueA, valueB, valueC ] = await Promise.all([ functionA(), functionB(), functionC() ])
  doSomethingWith(valueA)
  doSomethingElseWith(valueB)
  doAnotherThingWith(valueC)
}
```
