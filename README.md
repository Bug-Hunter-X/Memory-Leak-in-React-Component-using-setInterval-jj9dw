# React setInterval Memory Leak

This repository demonstrates a common mistake when using `setInterval` within a React component's `useEffect` hook: forgetting to clear the interval when the component unmounts. This leads to a memory leak and potential performance issues.

## Bug
The `bug.js` file contains a React component that uses `setInterval` to update a counter every second. However, it's missing the cleanup function in the `useEffect` hook's return statement to clear the interval when the component is unmounted. This causes the interval to continue running even after the component is no longer rendered, leading to a memory leak.

## Solution
The `bugSolution.js` file shows the correct way to use `setInterval` within `useEffect`. It includes a cleanup function that uses `clearInterval` to stop the interval when the component unmounts, preventing memory leaks.

## How to reproduce
1. Clone the repository
2. Run `npm install`
3. Run `npm start`
4. Observe the counter in the browser. Unmount the component (e.g., navigate away from the page) and check the console. The console output will show that the interval continues even after the component is unmounted. This will only be observable in the bug file.