# 2620. Counter

## Problem
Write a function `createCounter` that accepts an integer `n` and returns a counter function.

The returned function should:
- Return the current value of `n` when called.
- Increment `n` by `1` after each call.

## Approach
This problem is solved using a **closure**. A closure allows the returned function to retain access to the variable `n` even after `createCounter` has finished executing.

Each time the returned function is invoked:
1. It returns the current value of `n`.
2. It increments `n` using the post-increment operator (`n++`).

## Algorithm
1. Accept the initial value `n`.
2. Return an inner function.
3. Inside the inner function:
   - Return the current value of `n`.
   - Increment `n` for the next call.

## Code

```javascript
/**
 * @param {number} n
 * @return {Function}
 */
var createCounter = function(n) {
    return function() {
        return n++;
    };
};
```

## Example

```javascript
const counter = createCounter(10);

console.log(counter()); // 10
console.log(counter()); // 11
console.log(counter()); // 12
```

## Complexity Analysis
- **Time Complexity:** O(1) per function call.
- **Space Complexity:** O(1).

## Key Concept
A **closure** enables the inner function to remember and update the variable `n` across multiple function calls, making it ideal for implementing counters.
