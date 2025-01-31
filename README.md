# React useEffect Hook Missing Dependency

This repository demonstrates a common error in React applications: a missing dependency in the `useEffect` hook.  The `useEffect` hook is used to perform side effects in functional components, but if dependencies aren't correctly specified, it can lead to unexpected behavior, such as infinite loops or stale closures. 

The `bug.js` file contains the buggy code. The `bugSolution.js` file shows the corrected code with the missing dependency added.

## How to Reproduce

1. Clone this repository.
2. Run `npm install` to install the necessary packages.
3. Run `npm start` to start the development server.
4. Observe the console output and the behavior of the component. 

The buggy component will log to the console more frequently than expected, showcasing the infinite loop issue caused by the missing dependency.

## Solution

The solution is simply to include all variables used inside the `useEffect` hook that are not defined locally within the effect in the dependency array.  This ensures the effect only runs when those values change.