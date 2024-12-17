# React: Memory Leak in useEffect with setInterval

This repository demonstrates a common React bug involving memory leaks caused by the improper use of `setInterval` within the `useEffect` hook. The provided code lacks the necessary cleanup function to clear the interval when the component unmounts, leading to a memory leak and potential performance issues.

## Bug Description

The `MyComponent` uses `setInterval` to update a state variable every second. However, it fails to clear the interval using the return function from `useEffect`. This means that even after the component is unmounted, the interval continues to run, consuming resources and potentially causing memory leaks. 

## Solution

The solution addresses the memory leak by providing a cleanup function that uses `clearInterval` to stop the interval before the component is unmounted. This ensures that the interval is correctly cleared and prevents memory leaks.