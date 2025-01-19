# React setInterval Memory Leak

This repository demonstrates a common bug in React applications involving the improper use of `setInterval` within the `useEffect` hook, leading to memory leaks.  The `bug.js` file showcases the problematic code, while `bugSolution.js` provides the corrected implementation.

**Problem:** The original code uses `setInterval` to update a counter every second. However, it lacks a cleanup function to stop the interval when the component unmounts. This results in the interval continuing to run even after the component is no longer needed, leading to memory leaks.

**Solution:** The solution involves using the return value of `useEffect` to implement a cleanup function that calls `clearInterval` to stop the interval before the component unmounts.