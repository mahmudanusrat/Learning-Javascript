# Learning-Javascript

### What is promise?
In JavaScript, Promise are easy to manage when dealing with multiple asynchronous operations where callbacks can create callback hell leading to unmanageable code. Prior to promises events and callback functions were used but they had limited functionalities and created unmanageable code. Multiple callback functions would create callback hell that leads to unmanageable code. 

A promise has mainly 3 states:
+ **Unresolved:** Promise is still pending i.e. not fulfilled or rejected yet.
+ **Resolved:** Action related to the promise succeeded
+ **Rejected:** Action related to the promise failed

#### How to create a promise?

``` js

// Creating a Promise
const myPromise = new Promise((resolve, reject) => {
  setTimeout(() => {
    const success = true;
    if (success) {
      resolve("Operation completed successfully!"); 
    } else {
      reject("Operation failed!"); 
    }
  }, 2000);
});

// Using the Promise
myPromise
  .then((result) => {
    console.log("Success:", result);
  })
  .catch((error) => {
    console.log("Error:", error);
  });
```

### What is Async/await?
Async/Await simplifies working with promises, offering a cleaner syntax in asynchronous functions. The ‘await’ keyword, exclusive to async functions, pauses execution until the awaited promise resolves or rejects.



### Difference between promise and async/await.

Promise
+ Promise is an object representing intermediate state of operation which is guaranteed to complete its execution at some point in future.
+ Promise has 3 states – resolved, rejected and pending.
+ If the function “function1” is to executed after the promise, then promise.then(function1) continues execution of the current function after adding the fxn1 call to the callback chain.	
+ Error handling is done using .then() and .catch() methods.	
+ Promise chains can become difficult to understand sometimes.

Async/await
+ Async/Await is a syntactic sugar for promises, a wrapper making the code execute more synchronously.
+ It does not have any states. It returns a promise either resolved or rejected.
+ If the function “function1” is to executed after await, then await X() suspends execution of the current function and then fxn1 is executed.                                
+ Error handling is done using .try() and .catch() methods.
+ Using Async/Await makes it easier to read and understand the flow of the program as compared to promise chains.   

### When should we use async await and promise?

