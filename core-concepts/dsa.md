# DSA

## Data Structures

1. Arrays:
2. Linked Lists:
3. Stacks: push(), pop(), peek(), isEmpty(), printStack()
4. Queues: enqueue(), dequeue(), front(), isEmpty(), printQueue()
5. Trees:
6. Graphs:
7. Hash Map: get(), set(), has(), delete(), keys(), values()
8. Heaps:

## Algorithm

### Search
- Binary: repeatedly halve the sorted array eventually arriving to the target
- Linear: iterate until element matches target

### Sort
- Quick: selects a pivot element, partitions into 2 sub-arrays (smaller and greater elements) and then recursively sort
- Bubble: iterate through a list to find the greatest element and repeat until entire list is sorted

### Recursion 
- calls itself until a condition is met
- Use cases: search, sort, tree and graph traversal

### Greedy algo
- builds up solution step by step by selecting the best possible choice at each step without considering each choice or the consequences of this choices in future
- simple and efficient but not always optimal
- Use cases: Shortest Path

### Dynamic programming
- breaking it down into smaller sub problem and solving each subproblem only once and storing it for future use
- Approach
    - Memoization (Top down): stores solution to sub-problems and reuses them to avoid redundant caclculation
    - Tabulation (Bottom up): stores solution to sub-problems and use this computed results to build up main solution

### Back tracking
- incrementally building candidates for a solution and abadoning them if they don't lead to valid solution. brute force
- Steps
    - generate candidate
    - test candidate
    - backtrack
    - repeat
- Use cases: sudoku, crossword

### Worst case, best case, average case analysis

Complexities | O Notation | Time | space
------------ | ---------- | ---- | -----
Constant | O(1) | accessing element in an array | 
Logarithmic | O(log n) | binary search on sorted array | 
Linear | O(n) | iterating through each element in an array | 
Quadratic | O(n^2) | bubble sort, nested loops over array | storing 2d matrix
Exponential | O(2^n) | Brute force | 
