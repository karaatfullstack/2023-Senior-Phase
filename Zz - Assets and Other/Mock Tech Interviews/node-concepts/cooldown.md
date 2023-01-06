# Technical Mock Interview

## Overview

Create an API throttling function

### Question 



#### Cooldown API (20 mins)

Imagine you have a sensitive API that will shut down with too many requests. Create a higher-order function that takes a callback method  and returns a new version of that callback that can only be called once a cooldown period of 1 second has passed since it was last called.  


```javascript

const throttle = callback => {...}
```


#### Solution

```javascript

const throttle = func => {
  let time = Date.now() - 1000;
  let res
  return function(...args){
    if(Date.now() - time >= 1000){
      let res = func(...args)
      time = Date.now()
      return res
    } else {
      return res
    }
  }
}
```


### Notes

Good sub-questions to ask:

* What is a higher-order function?
* What is partial application?
* What if our callback requires arguments to be passed in?
* What if we only want our callback to be callable *once*?