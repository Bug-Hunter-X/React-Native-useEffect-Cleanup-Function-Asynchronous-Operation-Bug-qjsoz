# React Native useEffect Cleanup Function Asynchronous Operation Bug

This repository demonstrates a common, yet subtle bug in React Native involving asynchronous operations within the cleanup function of the `useEffect` hook.  When a component unmounts before an asynchronous cleanup task completes, it can lead to errors, unexpected behavior, or wasted resources. This example shows the problem and provides a solution using AbortController.

## Problem
The `bug.js` file showcases the problematic code where an asynchronous `fetch` call is used in the cleanup function.  If the component unmounts before the `fetch` is complete, the `abort()` might not successfully cancel the request, causing lingering effects.

## Solution
The `bugSolution.js` file presents a robust solution using `AbortController` to reliably cancel the asynchronous operation when the component unmounts. This prevents potential issues arising from continuing asynchronous operations after the component is no longer active.

## How to reproduce
1. Clone this repository.
2. Run `npm install`.
3. Run `npx react-native run-android` (or `npx react-native run-ios`) to run the app.
4. Observe the console logs for the bug and then for the solution.