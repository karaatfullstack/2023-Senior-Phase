# Technical Mock Interview

## Overview

Working with a codebase that is written in ES5 syntax might happen on the job. It is important to know how to identify how certain language constructs execute.

### Question

#### Title (30 mins)

What will the following code output?

```javascript
var arr = [10, 12, 15, 21] // Set as `var` because if it was `let`, it would give too much away
for (var i = 0; i < arr.length; i++) {
  setTimeout(function() {
    console.log('Index: ' + i + ', element: ' + arr[i])
  }, 3000);
}
```

#### Solution

Index: 4, element: undefined (printed 4 times)

It's important to note the `var`. The scope of `var` depends on where it is defined. Since, in ES5, there was no concept of block scope, `var` would either be in function scope or global scope. Since there is no function defined here as the for loop is considered a block, `var` exists globally

The setTimeout function creates a function (the closure) that has access to its outer scope, which is the loop that contains the index i. However, that same functions gets put on the event loop.

After 3 seconds go by, the function returns from the event loop, gets placed on the stack and executes and it prints out the value of i. The problem is that the for loop has already been looped through. Remember the loop goes through the entire length of the array which is 4 before the condition is actually broken. arr[4] does not exist, which is why you get undefined.

```javascript
let arr = [10, 12, 15, 21];
for (var i = 0; i < arr.length; i++) {
  // pass in the variable i so that each function
  // has access to the correct index
  // this is called in IIFE
  setTimeout(function(i_local) {
    return function() {
      console.log('The index of this number is: ' + i_local);
    }
  }(i), 3000);
}
```

OR

```javascript
let arr = [10, 12, 15, 21];
for (let i = 0; i < arr.length; i++) {
  // using the ES6 let syntax, it creates a new binding
  // every single time the function is called
  // read more here: http://exploringjs.com/es6/ch_variables.html#sec_let-const-loop-heads
  setTimeout(function() {
    console.log('The index of this number is: ' + i);
  }, 3000);
}
```

### Notes

Can reference from warm-ups:

- [Scope](../warm-ups/scope.md)
- [Closure](../warm-ups/closure.md)
- [Event Loop](../warm-ups/event-loop.md)

If the student gets stuck:

- Ask them what are the scopes and have them put the different scopes into buckets
- Remind them that there is a difference between ES6 vs. ES5 JavaScript
- Ask them what is "weird" or "off" about the code vs. how they normally write code specifically regarding variable declarations
