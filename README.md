# JavaScript setTimeout Loop Closure Issue

This repository demonstrates a common issue encountered when using `setTimeout` within a loop in JavaScript. The problem arises due to how closures work in JavaScript.

## Problem Description

The provided `bug.js` file contains a function `myFunction` that uses a `for` loop and `setTimeout`.  The intention is to log numbers 0 through 9 with a one-second delay between each log. However, due to the closure, all the timeouts will eventually log 10 (the final value of 'i') because by the time the `setTimeout` callbacks fire, the loop has already finished and 'i' has reached its final value.

## Solution

The `bugSolution.js` file shows how to solve this issue using an immediately invoked function expression (IIFE) to create a new scope for each iteration of the loop, ensuring that each timeout gets its own copy of 'i'.