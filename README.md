# React useEffect Infinite Loop Bug

This repository demonstrates a common bug in React applications: an infinite loop caused by improperly using the `useEffect` hook.  The `useEffect` hook, while powerful, can lead to unexpected behavior if not used correctly.  This example shows how updating state within the `useEffect` without a dependency array leads to a continuous re-render and, subsequently, an infinite loop.

## Bug Description
The bug lies in the `MyComponent` function's `useEffect` hook. The effect tries to update the `count` state with `setCount(count + 1)`, triggering a re-render.  Because the effect has no dependencies, it runs after every render, creating an infinite loop of state updates and re-renders.

## Solution
The solution involves carefully managing dependencies in the `useEffect` hook. By including `count` in the dependency array, the effect will only run when the `count` changes.  In this case, we intend to run the effect only when the component mounts, hence the empty dependency array is used in the improved implementation.