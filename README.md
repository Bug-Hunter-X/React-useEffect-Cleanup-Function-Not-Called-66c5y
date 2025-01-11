# React useEffect Cleanup Function Not Called

This repository demonstrates a common error in React's `useEffect` hook where the cleanup function isn't called when the component unmounts.  This can lead to memory leaks, especially when dealing with subscriptions, timers, or event listeners. 

The `bug.js` file contains the problematic code. The `bugSolution.js` file shows the corrected version. 

## How to reproduce the bug

1. Clone this repository.
2. Run `npm install` to install dependencies.
3. Run `npm start` to start the development server.
4. Observe the console logs. When the component is unmounted, the cleanup message isn't shown indicating the bug.

## How to fix the bug

The key is to ensure that the return statement within the `useEffect` hook correctly cleans up after itself.  In the corrected code (`bugSolution.js`), we added a return function which logs a message when component unmounts. This function is automatically called by React before the component is destroyed, preventing resource leaks.
