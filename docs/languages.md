# Programming Languages

## Javascript

### Intro

### Data Types:
- Primitive: Number, BigInt, String, Boolean, Null, Undefined, Symbol
- Non-primitive: Array, Objects, Functions

### Closures: 
- A function inside another function allowing access to variables defined in enclosing function even after it is finished executing. 
- Uses: encapsulation, callback function

### Higher Order Functions: 
- A function that either takes other functions as an argument or returns a function or both.
- Eg: map, filter, decorator function

### Function methods
Used for setting this context explicitly

```Javascript
function greet(greeting) { console.log(`${greeting}, ${this.name}!`) }
const user = { name: 'Alice' }

// Invoke functions with specific `this`
greet.call(user, 'Hello') 					// Hello, Alice!
greet.apply(user, ['Hi']) 					// Hi, Alice!

// Creates a new function with a fixed `this`
const greetUser = greet.bind(user, 'Hey') 	
greetUser() 								// Hey, Alice!
```

### Asynchronous operations

| Feature            | Callbacks        | Promises          | Async/Await       |
|--------------------|------------------|-------------------|-------------------|
| Syntax             | More complex     | Moderate          | Easier            |
| Error Handling     | Manual           | Built-in `catch`  | `try/catch`       |
| Readability        | Poor             | Better            | Best              |
| Code Structure     | Callback hell    | Chaining          | Sequential        |
| Compatibility      | Widely supported | Widely supported  | Modern browsers   |
| Error Handling     | Complex          | Easier            | Easier            |
| Use Cases		| legacy code, chaining	| frequent ops		| sequence of async operations	|

#### Promise:
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

### Objects
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



## Typescript

### Intro
- Superset of JavaScript that adds static typing
- Compiles to JavaScript
- Provides type safety and better tooling
- Developed and maintained by Microsoft

### Data Types:
- Primitive: number, string, boolean, null, undefined, symbol, bigint
- Non-primitive: array, object, function
- Additional: any, unknown, never, void, enum, tuple

### Type System:

```typescript
// Basic Types
let name: string = "John";
let age: number = 30;
let isActive: boolean = true;

// Arrays
let numbers: number[] = [1, 2, 3];
let strings: Array<string> = ["a", "b"];

// Objects
interface User {
    name: string;
    age: number;
    email?: string;  // Optional property
    readonly id: number;  // Read-only property
}

// Functions
function greet(name: string): string {
    return `Hello, ${name}!`;
}

// Type Aliases
type Point = {
    x: number;
    y: number;
};
```

### Generics:

- Reusable components that work with multiple types

```typescript
function identity<T>(arg: T): T {
    return arg;
}

// Usage
let output = identity<string>("hello");
let num = identity<number>(42);
```

### Classes and Interfaces:

```typescript
interface Animal {
    name: string;
    makeSound(): void;
}

class Dog implements Animal {
    constructor(public name: string) {}
    
    makeSound(): void {
        console.log("Woof!");
    }
}
```

### Type Assertions:

```typescript
let someValue: unknown = "this is a string";
let strLength: number = (someValue as string).length;
```

### Utility Types:

| Type | Description | Example |
|------|-------------|---------|
| Partial<T> | Makes all properties optional | `Partial<User>` |
| Required<T> | Makes all properties required | `Required<User>` |
| Readonly<T> | Makes all properties readonly | `Readonly<User>` |
| Pick<T,K> | Picks set of properties | `Pick<User, 'name' \| 'age'>` |
| Omit<T,K> | Omits set of properties | `Omit<User, 'email'>` |

### Advanced Types:

```typescript
// Union Types
type StringOrNumber = string | number;

// Intersection Types
type Employee = Person & Worker;

// Type Guards
function isString(value: any): value is string {
    return typeof value === "string";
}

// Mapped Types
type Readonly<T> = {
    readonly [P in keyof T]: T[P];
};

// Conditional Types
type NonNullable<T> = T extends null | undefined ? never : T;
```

### Decorators:

- Experimental feature that allows adding annotations to classes and members
```typescript
function log(target: any) {
    console.log(`Class ${target.name} is defined`);
}

// Method Decorator
function enumerable(value: boolean) {
    return function (target: any, propertyKey: string, descriptor: PropertyDescriptor) {
        descriptor.enumerable = value;
    };
}

@log
class Example {
    @enumerable(false)
    method() {}
}
```

### Module System:

```typescript
// Named exports
export const config = { apiKey: "123" };
export function helper() {}

// Default export
export default class Main {}

// Re-exports
export * from './other-module';

// Dynamic imports
const module = await import('./module');
```

### TypeScript Configuration:

```json
{
  "compilerOptions": {
    "target": "ES2020",
    "module": "ESNext",
    "strict": true,
    "esModuleInterop": true,
    "skipLibCheck": true,
    "forceConsistentCasingInFileNames": true
  }
}
```

### Best Practices:

- Use strict mode
- Prefer interfaces over type aliases for objects
- Use readonly when possible
- Avoid any type
- Use type guards for runtime checks
- Leverage utility types
- Use const assertions
- Implement proper error handling

### Testing with TypeScript:

```typescript
import { describe, it, expect } from 'jest';

describe('Calculator', () => {
    it('should add two numbers', () => {
        expect(add(2, 3)).toBe(5);
    });
});
```

### Performance Considerations:
- Use const assertions for literal types
- Avoid unnecessary type assertions
- Use proper type narrowing
- Leverage compiler optimizations
- Use proper module bundling
- Implement tree shaking
- Use proper source maps


## Python

### Intro

- Interpreted, high-level programming language
- Emphasizes code readability with significant indentation
- Dynamic typing and garbage collection

### Data Types:

- Primitive: int, float, str, bool, None
- Non-primitive: list, tuple, dict, set, function
- Special: bytes, bytearray, frozenset

### Memory Management:

- Reference counting for garbage collection
- Generational garbage collection
- Memory views and buffer protocol

### Context Managers:

```python
# Using with statement
with open('file.txt', 'r') as file:
    content = file.read()

# Custom context manager
class DatabaseConnection:
    def __enter__(self):
        print("Opening connection")
        return self
    
    def __exit__(self, exc_type, exc_val, exc_tb):
        print("Closing connection")
```

### Decorators:

- Functions that modify behavior of other functions
- Uses: logging, timing, access control, caching

```python
def timer(func):
    def wrapper(*args, **kwargs):
        start = time.time()
        result = func(*args, **kwargs)
        end = time.time()
        print(f"Function {func.__name__} took {end-start} seconds")
        return result
    return wrapper

@timer
def slow_function():
    time.sleep(1)
```

### Metaclasses:

- Classes for classes
- Used for API design, ORM, validation

```python
class Meta(type):
    def __new__(cls, name, bases, attrs):
        # Modify class creation
        return super().__new__(cls, name, bases, attrs)

class MyClass(metaclass=Meta):
    pass
```

### Asynchronous Programming:

| Feature            | Threading        | Multiprocessing  | Async/Await      |
|--------------------|------------------|------------------|------------------|
| Best for          | I/O-bound tasks  | CPU-bound tasks  | I/O-bound tasks  |
| Memory            | Shared          | Separate        | Shared          |
| Complexity        | Moderate        | High            | Low             |
| Use Cases         | Network I/O     | Heavy computation| Web servers     |

### Async/Await:

```python
import asyncio

async def main():
    async with aiohttp.ClientSession() as session:
        async with session.get('http://api.example.com') as response:
            return await response.json()

# Running async code
asyncio.run(main())
```

### Data Structures and Algorithms:

| Structure | Time Complexity | Use Cases |
|-----------|----------------|-----------|
| List      | O(1) access    | Dynamic arrays, stacks |
| Dict      | O(1) lookup    | Key-value storage, caches |
| Set       | O(1) lookup    | Unique collections, membership testing |
| Deque     | O(1) both ends | Queues, sliding windows |

### Package Management:

```python
# requirements.txt
requests==2.28.1
pandas>=1.4.0
numpy~=1.21.0

# setup.py
from setuptools import setup

setup(
    name="my_package",
    version="0.1.0",
    packages=["my_package"],
    install_requires=["requests>=2.28.1"]
)
```

### Testing:

```python
import unittest

class TestCalculator(unittest.TestCase):
    def setUp(self):
        self.calc = Calculator()
    
    def test_addition(self):
        self.assertEqual(self.calc.add(2, 3), 5)
    
    def tearDown(self):
        del self.calc
```

### Performance Optimization:

- List comprehensions over loops
- Generator expressions for memory efficiency
- `__slots__` for memory optimization
- Cython for performance-critical code
- Profiling with cProfile and line_profiler

### Higher Order Functions:

- Functions that take other functions as arguments or return functions
- Eg: map, filter, reduce, decorator functions

### Function methods

```python
def greet(self, greeting):
    print(f"{greeting}, {self.name}!")

class User:
    def __init__(self, name):
        self.name = name

user = User("Alice")

# Method binding
greet(user, "Hello")  # Hello, Alice!
```

### Classes and Inheritance

- `__init__` - constructor method
- Multiple Inheritance

```python
class Animal:
    def __init__(self):
        self.eats = True

class Rabbit(Animal):
    def __init__(self):
        super().__init__()
        self.jumps = True
```

### Data Structures

| Feature | List | Tuple | Dict | Set |
|---------|------|-------|------|-----|
| Mutable | Yes  | No    | Yes  | Yes |
| Ordered | Yes  | Yes   | Yes* | No  |
| Indexed | Yes  | Yes   | Yes  | No  |
| Use Cases | - Collection of items | - Immutable sequences | - Key-value pairs | - Unique values |
| | - Dynamic arrays | - Data that shouldn't change | - Fast lookups | - Set operations |

*Python 3.7+ maintains insertion order

