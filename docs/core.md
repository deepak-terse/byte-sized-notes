# Core Fundamentals

## Data Structures

- Array
- Linked List
- Stack
- Queue
- Hash Table

## Algorithmic Complexity

### Space vs Time Complexity

### Asymptotic Notations

- Big O (O): worst case
- Big Theta (θ): average case
- Big Omega (Ω): best case

### Common Runtimes

- Constant
- Logarithmic
- Linear
- Exponential
- Factorial

## Algorithm

### Sorting

- Bubble
- Selection
- Insertion
- Merge
- Quick

### Searching

- Linear
- Binary

## Programming Paradigm:
Style or way of thinking about programming

### Imperative
- Step-by-step instructions (“how to do it”).
- Eg: using for loops to update an array.

### Declarative
- State what you want, not how.
- Eg: `arr.map(x => x * 2)` instead of manual looping.

### Functional
- Focus on pure functions, immutability, composition.
- Eg: filter, map, reduce.

### Object-Oriented
- Organize code into objects with state + behavior.
- Eg: `class User { login() { ... } }`

### Event-Driven
- Code reacts to events.
- Eg: `button.addEventListener('click', handler)`.


## Design Patterns
Repeatable solution to commonly occurring problems

### Creational

- Singleton:
  - single instance throughout application
  - uc: database connections, logging, configuration

- Factory:
  - interface for creating objects without specifying exact class
  - uc: UI components, database drivers, payment processors

- Builder:
  - step-by-step creation offering multiple variations
  - uc: SQL query builder, configuration objects, complex forms

- Prototype:
  - creates objects by copying existing instances
  - uc: game objects, document templates, configuration cloning

### Structural

- Adapter:
  - converts one interface into another
  - uc: third-party libraries, legacy code integration

- Composite:
  - composes objects in tree structure to represent hierarchies
  - uc: file systems, GUI components, organizational charts

- Decorator:
  - adds new behaviors to objects by wrapping them
  - uc: middleware, UI enhancements, feature toggles

- Facade:
  - provides simplified interface to complex subsystem
  - uc: API wrappers, library interfaces, system integration

### Behavioral

- Observer:
  - notifies dependent objects when subject changes
  - uc: event systems, MVC architecture, real-time updates

- Strategy:
  - defines multiple algorithms and selects one at runtime
  - uc: sorting algorithms, payment methods, compression

- Command:
  - encapsulates request as an object for queuing and logging
  - uc: undo/redo, task scheduling, remote operations

- Chain of Responsibility:
  - passes request through chain of handlers until one handles it
  - uc: middleware, validation chains, support escalation

## Design Principles
Fundamental guidelines and recommendations for creating software that is scalable, maintainable, readable, and efficient

### SOLID Principles:

- S - Single Responsibility: 
  - class should have only one reason to change
  - FP: write small pure functions
  - Eg: `filter(isEven, nums)` (just filters, not logs)

- O - Open/Closed: 
  - open for extension, closed for modification
  - FP: use composition or higher order functions
  - Eg: `map(fn, arr)` works for any fn without changing map

- L - Liskov Substitution: 
  - derived classes must be substitutable for base classes
  - FP: any function with the same input/output contract can be swapped.
  - Eg: `arr.map(toUpper)` vs `arr.map(trim)` → both (string) => string

- I - Interface Segregation:
  - clients shouldn't depend on unused interfaces
  - FP: expect only minimal data shape.
  - Eg: `getUserName({id, name})` instead of full user with 20 props.

- D - Dependency Inversion: 
  - depend on abstractions, not concretions
  - FP: injection dependency in arguments
  - Eg: `loadData(fetchFn)` instead of hardcoding fetch

### DRY (Don't Repeat Yourself):
  - avoid code duplication by extracting common functionality
  - improves maintainability and reduces bugs

### KISS (Keep It Simple, Stupid):
  - prefer simple solutions over complex ones
  - easier to understand, test, and maintain

### YAGNI (You Aren't Gonna Need It):
  - don't implement features until actually needed
  - prevents over-engineering and wasted effort

### Composition over Inheritance:
  - favor object composition over class inheritance
  - more flexible and avoids inheritance pitfalls

### Law of Demeter (Principle of Least Knowledge):
  - object should only talk to its immediate friends
  - reduces coupling between components

### Separation of Concerns:
  - divide program into distinct sections with minimal overlap
  - each section addresses separate concern