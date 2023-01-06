# Technical Mock Interview

## Overview

Scope is a central concept in JavaScript

### Question

#### Title (3 mins)

What is scope and whiteboard examples of scope and variable accessibility

#### Solution

```js
// Global Scope
const global = 'global'

// Function scope
function hello() {
    let someString = 'hello'
}

// Block Scope
for(let i = 0; i < 5; i++) {
    console.log(i)
}
```

### Notes

Could be a good time to ask about how `var` fits into this.
