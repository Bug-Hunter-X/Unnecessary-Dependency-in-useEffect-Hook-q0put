# Unnecessary Dependency in useEffect Hook

This example demonstrates a common error in React's `useEffect` hook: including unnecessary dependencies in the dependency array.  This leads to unexpected re-renders and performance issues.

## Problem

The `useEffect` hook in `bug.js` has the `count` variable in its dependency array.  While it seems logical to include this, the effect's purpose (logging 'Mounted') should only run once when the component mounts.  Including `count` causes the effect to re-run on every click, leading to the console log being printed repeatedly.

## Solution

`bugSolution.js` shows the correct way. An empty dependency array `[]` ensures the effect runs only once on mount.