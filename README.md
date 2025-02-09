# React 19 useEffect Dependency Array Issue

This repository demonstrates a common error related to the `useEffect` hook in React 19.  The issue arises when the dependency array is improperly configured, leading to unexpected re-renders and potential performance problems.

## Problem
The initial `bug.js` code shows a `useEffect` hook that's intended to log the current count to the console. However, the `count` variable is missing from the dependency array. As a result, the effect runs on every render, causing an infinite loop because `setCount` triggers a re-render, and `useEffect` runs again, triggering further re-renders. 

## Solution
The `bugSolution.js` file corrects the error by adding `count` to the dependency array. Now, the `useEffect` hook only runs when the `count` value changes.