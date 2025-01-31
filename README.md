# React useEffect setInterval Memory Leak
This example demonstrates a common mistake in React's `useEffect` hook: forgetting to clear an interval when the component unmounts.  This leads to memory leaks and unexpected behavior.

The `bug.js` file shows the faulty code, while `bugSolution.js` provides the corrected version.

## Problem
The `setInterval` function within the `useEffect` hook starts an interval that continues to update the state even after the component is unmounted. This is a classic cause of memory leaks in React applications.

## Solution
The solution involves using the return value of `useEffect` to implement a cleanup function.  This function is automatically called when the component unmounts or when the dependencies array changes, allowing us to clear the interval using `clearInterval`.