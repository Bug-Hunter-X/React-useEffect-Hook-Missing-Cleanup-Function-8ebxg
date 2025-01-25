# React useEffect Hook Missing Cleanup Function

This example demonstrates a common error in React's `useEffect` hook: forgetting to include a cleanup function for subscriptions or event listeners.  Failure to return a cleanup function from `useEffect` can result in memory leaks and unexpected behavior when the component unmounts.

The bug.js file contains the problematic code, and bugSolution.js provides the corrected version.

## Bug
The `useEffect` hook in `bug.js` logs a message when the component mounts, but it doesn't handle cleanup when the component unmounts, causing a potential memory leak if the component is frequently rendered and unrendered.

## Solution
The `bugSolution.js` file fixes this by adding a return statement inside `useEffect`, which includes a cleanup function that executes when the component unmounts.  In this simple example, it's just an empty function, but in more complex scenarios, it would handle things like removing event listeners or cancelling subscriptions.