# Technical Mock Interview

## Overview

Find the depth of a BST node

### Question 

#### Find Node Depth (15 mins)

Given the root of a BST and a value, determine the depth of the node with that value. 


#### Solution


```javascript

const getDepth = (val, node = root, depth = 0) => {
    if(val === node.val){
      return depth
    } else if (val < node.val) {
      return getDepth(val, node.left, depth + 1)
    } else {
      return getDepth(val, node.right, depth + 1)
    }
}
```


### Notes

Good sub-questions to ask:

* What if the value isn't in the tree?

* What if there are multiple nodes with that value?
