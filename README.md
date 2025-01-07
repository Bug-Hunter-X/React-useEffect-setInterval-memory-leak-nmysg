# React useEffect setInterval memory leak
This example demonstrates a common mistake when using the `setInterval` function within a React `useEffect` hook.  Forgetting to include a cleanup function leads to memory leaks as the interval continues to run even after the component is unmounted.

## Bug
The `bug.js` file contains the buggy code.  The `setInterval` function is used to update a counter every second. However, no cleanup function is provided in the `useEffect` hook. This means the interval will persist even after the component is unmounted, consuming resources and potentially causing memory issues.

## Solution
The `bugSolution.js` file demonstrates the corrected code.  A cleanup function is added to the `useEffect` hook, using `clearInterval` to stop the interval when the component unmounts. This effectively prevents the memory leak.