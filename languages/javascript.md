# Javascript

## Intro

## Data Types:
- Primitive: Number, BigInt, String, Boolean, Null, Undefined, Symbol
- Non=primitive: Array, Objects, Functions

## Closures: 
- A function inside another function allowing access to variables defined in enclosing function even after it is finished executing. 
- Uses: encapsulation, callback function

## Higher Order Functions: 
- A function that either takes other functions as an argument or returns a function or both.
- Eg: map, filter, decorator function

## Function methods
Used for setting this context explicitly

```Javascript
function greet(greeting) { console.log(`${greeting}, ${this.name}!`) }
const user = { name: 'Alice' };

// Invoke functions with specific `this`
greet.call(user, 'Hello'); 					// Hello, Alice!
greet.apply(user, ['Hi']); 					// Hi, Alice!

// Creates a new function with a fixed `this`
const greetUser = greet.bind(user, 'Hey') 	
greetUser(); 								// Hey, Alice!
```

## Asynchronous operations
| Feature            | Callbacks        | Promises          | Async/Await       |
|--------------------|------------------|-------------------|-------------------|
| Syntax             | More complex     | Moderate          | Easier            |
| Error Handling     | Manual           | Built-in `catch`  | `try/catch`       |
| Readability        | Poor             | Better            | Best              |
| Code Structure     | Callback hell    | Chaining          | Sequential        |
| Compatibility      | Widely supported | Widely supported  | Modern browsers   |
| Error Handling     | Complex          | Easier            | Easier            |
| Use Cases		| legacy code, chaining	| frequent ops		| sequence of async operations	|

### Promise:
- State: Pending, Fulfilled, Rejected
- Result values: Undefined, Value, Error
	```Javascript
	const promise = new Promise((resolve, reject) => {
		resolve()				// success
		reject(new Error())		// failure
	})

	promise.then(
		result => {},
		error => {}
	)

	promise
		.then(result => {})
		.catch(error => {})
		.finally(() => {})
	```

- Handling multiple promises
	```Javascript
	// Parallel Execution
	Promise.all([...promises]) 	// returns all resolved promise result
	Promise.any([...promises]) 	// returns first resolved promise result
	Promise.allSettled([...promises])	// returns status, value and reason of all promises
	Promise.race([...promises]) 			// returns response of first promise to be settled

	// Sequential Execution
	promise1.then(result1 => {
		return promise2;
	}).then(result2 => {
		return promise3
	}).then(result3 => {
		// sucess
	}).catch(error => {
		// error handling
	})
	```

## Objects
- new keyword - create this object and return implicitly
- Prototypal Inheritance
	- Objects have special hidden property `[[Prototype]]` that is either null or references 
	another object.
	```Javascript
	let animal = { eats: true };
	let rabbit = { jumps: true };
	
	Object.setPrototypeOf(rabbit, animal) 
	Object.getPrototypeOf(rabbit) // animal
	```

| Feature | Map | Set |
|---------|-----|-----|
| Description | Key-value pairs container | Collection of unique values |
| Keys/Values | Can be any value (primitive or object) | Must be unique values |
| Iteration order | Maintains insertion order | Iteration order based on insertion order |
| Use Cases | - Storing data with associated keys | - Removing duplicates from an array |
| | - Maintaining order of insertion | - Checking for presence of a value |
| | - Easy lookup of values by key | - Ensuring uniqueness of values |
