# JavaScript Closure Issue in setTimeout Loop

This repository demonstrates a common JavaScript error related to closures within `setTimeout` loops. The problem arises when a variable declared outside the `setTimeout` function is accessed from within the callback function.  The asynchronous nature of `setTimeout` can cause the value of the variable to change unexpectedly by the time the callback function executes.

## The Bug

The `bug.js` file contains a function `myFunction` which demonstrates the issue. The intention is to log numbers from 0 to 9 with a 1-second delay between each log. However, due to the closure issue, the final value of `i` (which is 10) will be logged 10 times instead of the expected sequence of numbers.

## The Solution

The `bugSolution.js` file provides a corrected version of `myFunction`. By using `let` within the loop to create a new variable for each iteration, we ensure that each callback function correctly captures its own value of `i`.

This example helps illustrate a fundamental concept of how closures interact with asynchronous operations in JavaScript, a pitfall that can lead to difficult-to-debug errors in complex code.