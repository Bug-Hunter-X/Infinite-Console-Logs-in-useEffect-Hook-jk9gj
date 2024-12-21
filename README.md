# React useEffect Infinite Loop Bug

This repository demonstrates a common error in React's `useEffect` hook: an infinite loop caused by improperly handling dependencies.  The `useEffect` hook, when provided with an empty dependency array (`[]`), is intended to run only once after the initial render.  However, if the effect itself triggers a re-render (directly or indirectly), it creates an infinite loop, leading to performance issues or application crashes.

## The Problem

The provided code logs the current count to the console within the `useEffect` hook.  Even though the dependency array is empty, the `setCount` function indirectly triggers re-renders.  This results in the effect continuously re-running, leading to an infinite loop of console logs.

## The Solution

The solution is to include `count` in the dependency array.  This ensures the effect only runs when the value of `count` changes. 

## How to reproduce the issue
1. Clone the repository.
2. Run `npm install` to install the necessary dependencies.
3. Run `npm start` to start the development server.
4. Open your browser and observe the console. You'll see the count logging infinitely.

## How to fix the issue
1. Replace the content in `bug.js` with the content of `bugSolution.js`.