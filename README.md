# React 19 useEffect Bug: Missing Dependency Array

This repository demonstrates a common error in React 19's `useEffect` hook: omitting the dependency array, leading to an infinite loop.  The `bug.js` file contains the buggy code, while `bugSolution.js` provides the corrected version.

## Problem
The `setInterval` function within the `useEffect` hook continuously updates the state, triggering re-renders and subsequently calling `useEffect` again, leading to an infinite loop and performance issues. This is because React doesn't know what values to watch to determine whether to rerun this effect.

## Solution
The correct solution involves adding an empty dependency array (`[]`) to `useEffect` to ensure the effect runs only once after the initial render.  If you need the effect to run based on specific values, include those values in the dependency array.  In other cases, you should consider using `useRef` or other techniques depending on the desired behavior.