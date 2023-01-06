# Technical Mock Interview

## Overview

### Question

#### Title (X mins)

- What is the event loop?
- In what order will these lines execute?

```js
// Example 1
console.log('Examples are fun')
setTimeout(
    () => {
        console.log('Hello')
    },
    0
)
console.log('Asynchronicity is fun!')
```

```js
// Example 2
console.log('Beginning of file')

setTimeout(
    () => {
        console.log('1. Hello, I will be timing out for 4.0 seconds')
    },
    4000
)

setTimeout(
    () => {
        console.log('2. Hello, I will be timing out for 5.0 seconds')
    },
    5000
)

setTimeout(
    () => {
        console.log('3. Hello, I will be timing out for 3.0 seconds')
    },
    3000
)

setTimeout(
    () => {
        console.log('4. Hello, I will be timing out for 2.0 seconds')
    },
    2000
)

setTimeout(
    () => {
        console.log('5. Hello, I will be timing out for 5.0 seconds 2')
    },
    5000
)

console.log('End of file')
```

#### Solution

The event loop is how JavaScript deals with asynchronous code. It consists of the event queue and a process (called the event loop) in which it takes whatever is in the event queue and puts it into the call stack after the call stack is empty. If we didn't have this construct asyc code such as timoutes, intervals, and promises would halt our entire application until it is done running.

##### Example 1

1. Examples are fun
2. Asynchronicity is fun
3. Hello

##### Example 2

```markdown
- Beginning of file
- End of file
- 4. Hello, I will be timing out for 2.0 seconds
- 3. Hello, I will be timing out for 3.0 seconds
- 1. Hello, I will be timing out for 4.0 seconds
- 2. Hello, I will be timing out for 5.0 seconds
- 5. Hello, I will be timing out for 5.0 seconds 2
```

### Notes

- Something to note is that as of ES6 there is something called the Job Queue (or also called the Promise Queue) that deals with Promises. It takes precendence over the Event Queue.
