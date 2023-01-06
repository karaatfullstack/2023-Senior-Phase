# Technical Mock Interview

## Overview

`setState` is central to how React updates the UI. It is important to know what the process looks like.

### Question

#### Describe in as many details as possible, what happens when you call `setState` (5 minutes)

#### Solution

1. Merge (create a copy) the object passed into `setState` into current state of component
2. `render()` is called and React will construct a tree of React elements
3. React will then "diff" (using their algorithm) the new tree with the previous tree
4. Make appropriate changes to UI

### Notes

- Steps 2-4 is a process called ["Reconcilation"](https://reactjs.org/docs/reconciliation.html)