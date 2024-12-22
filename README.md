# React useEffect Infinite Loop Bug

This repository demonstrates a common bug in React applications involving the `useEffect` hook. The bug causes an uncontrolled infinite loop due to the improper use of the dependency array in `useEffect`.

## Bug Description

The `useEffect` hook in the provided component lacks a dependency array.  This means the effect runs after every render, causing a state update (`setCount`) which, in turn, triggers another render.  This creates an infinite loop that crashes the application.

## Bug Solution

The solution involves adding a dependency array to the `useEffect` hook. The dependency array specifies which values the effect should depend on. If none of the values in the array change, the effect will not re-run.  In this case, we only want the effect to run when the `count` changes, so we add `[count]` as the dependency array.