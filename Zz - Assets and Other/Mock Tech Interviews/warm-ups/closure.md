# Technical Mock Interview

## Overview

Closure is a central concept in JavaScript

### Question

#### Title (3 mins)

What is closure and give an example?

#### Solution

Closure is the ability of a function to "remember" its lexical scope even though that function is being run outside of that lexical scope.

```js

function outer () {
    let counter = 0
    function inner() {
        return counter += 2
    }
    return inner
}

let newInstance = outer()
newInstance() // Increment counter
newInstance() // Increment counter
```

### Notes

* N/A
