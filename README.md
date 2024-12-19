# JavaScript Closure Issue in setTimeout Loop

This example demonstrates a common issue with closures in JavaScript's `setTimeout` function within a loop.  The expected behavior is to log the numbers 0 through 9, each after a one-second delay. However, due to the way closures work, the code outputs 10 ten times.

The problem is that the `setTimeout` callbacks don't capture the value of `i` at the time they're created; instead, they capture a reference to the variable `i`. By the time the callbacks finally execute, the loop has already completed, and `i` has its final value of 10.

The `bugSolution.js` file demonstrates how to solve this issue using an immediately invoked function expression (IIFE) to create a new scope for each iteration, ensuring that each callback captures its own copy of `i`.