# Learning-Javascript

### What is promise?
In JavaScript, Promise are easy to manage when dealing with multiple asynchronous operations where callbacks can create callback hell leading to unmanageable code. Prior to promises events and callback functions were used but they had limited functionalities and created unmanageable code. 
A promise has mainly 3 states:
+ **Pending:** Promise is still pending i.e. not fulfilled or rejected yet.
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
### What is callabck hell?
Callback hell refers to a situation where multiple nested callbacks make the code more difficult to read and understand.

### What is Async/await?
Async/Await simplifies working with promises, offering a cleaner syntax in asynchronous functions. The ‘await’ keyword, exclusive to async functions, pauses execution until the awaited promise resolves or rejects.
In async/await, The await keyword is used to wait for a promise to be resolved before continuing with the execution of the function. The await keyword can only be used inside an async function.

``` js
function asynchronous_operational_method() {
	let first_promise = 
		new Promise((resolve, reject) => resolve("Hello"));
	let second_promise = 
		new Promise((resolve, reject) => {
		setTimeout(() => {
			resolve(" GeeksforGeeks..");
		}, 1000);
	});
	let combined_promise = 
		Promise.all([first_promise, second_promise]);
	return combined_promise;
}

async function display() {
	let data = await asynchronous_operational_method();
	console.log(data);
}

display();
```


### Difference between promise and async/await.

Promise
+ Promise is an object representing intermediate state of operation which is guaranteed to complete its execution at some point in future.
+ Promise has 3 states – resolved, rejected and pending.
+ If the function “function1” is to executed after the promise, then promise.then(function1) continues execution of the current function after adding the function1 call to the callback chain.	
+ Error handling is done using .then() and .catch() methods.	
+ Promise chains can become difficult to understand sometimes.

Async/await
+ Async/Await is a syntactic sugar for promises, a wrapper making the code execute more synchronously.
+ It does not have any states. It returns a promise either resolved or rejected.
+ If the function “function1” is to executed after await, then await X() suspends execution of the current function and then fxn1 is executed.                                
+ Error handling is done using .try() and .catch() methods.
+ Using Async/Await makes it easier to read and understand the flow of the program as compared to promise chains.   

### When should we use async/await and promise?
When to use Promises:
+ When working with code that is promise-based.
+ When you need more control over the execution flow using .then() and .catch().
+ When you want to take advantage of some promise-specific features, like Promise.all().

When to use Async/Await:
+ When writing asynchronous code in a more synchronous style for improved readability.
+ When dealing with multiple asynchronous operations in a more sequential and cleaner way.
+ When you want to handle errors using try-catch, which can result in more readable error handling.



