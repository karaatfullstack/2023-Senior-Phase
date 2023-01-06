# Package Installation

Time: 30 minutes

## Overview

This problem is modeled after dependency installations or build orders. It is a directed, acyclic graph traversal, where the graph represents a dependency tree.

### Prompt

#### Problem Statement

Write a function `orderInstalls` that takes in an array of strings, representing the names of packages a user would like to install. These packages may or may not have any dependencies. The function should return a valid installation order (duplicates removed), such that all dependencies of each package are listed first. There may be multiple valid solutions to a given input.

#### Givens and Assumptions

You can assume you have access to a global variable `dependencies` that stores all dependencies of each package as an adjacency list:

```js
// NOTE: the interviewer may use this as reference.
// ideally, the interviewee will construct their own adj list
// and populate it with sample data, but this example can
// be shared as a hint if the interviewee is stuck

const dependencies = {
  'a': ['b'],
  'b': ['e', 'c', 'd'],
  'c': [],
  'd': [],
  'e': ['d']
}
```

You can also assume that all packages passed as input are listed in `dependencies`, and that there are no circular dependencies.

#### Sample Input/Output:

Example 1:
```js
let result = orderInstalls(['a', 'b']);
console.log(result); // c d e b a
// Other valid results:
// d c e b a
// d e c b a
```

Example 2:
```js
let result = orderInstalls(['e']);
console.log(result); // d e
// No other valid results
```

### Solution

The best way to approach this problem is recursively. This approach will use a hash table (`seen`) to optimize for time complexity:

```js
let seen = {};
const orderInstalls = (packages, result = []) => {
  for (let pkg of packages) {
    if(dependencies[pkg].length === 0) {
      if(!seen[pkg]) {
        result.push(pkg);
        seen[pkg] = true;
      }
    } else {
      orderInstalls(dependencies[pkg], result)
      if(!seen[pkg]) {
        result.push(pkg);
        seen[pkg] = true;
      }
    }
  }
  return result;
}
```

Solution steps:
* The solution takes in an array of `packages`, and a `result`, which is an accumulator for the final result as we recurse through the problem (this could be a global variable as well)
* Loop through all packages in the `packages` input array
* If a package has _no dependencies_, it can be installed immediately; it is pushed to the `result`
  * This is the base case
* Else, the package has dependencies, so we need to evaluate if those packages have dependencies as well.
  * This is the recursive case... as long as a package still has dependencies, we need to recursively check each of those packages for more dependencies until we reach the base case above.
  * Once this recursive call stack unwinds, we need to push the package we are _currently inspecting_ to the `result` list (by the time we reach this step, we've already added all its dependencies to the `result`)

Some interviewees will choose to prepend each package to the `result` before evaluating dependencies:

```js
let seen = {};
const orderInstalls = (packages, result = []) => {
  for (let pkg of packages) {
    if(!seen[pkg]) {
      result.unshift(pkg);
      seen[pkg] = true;
      orderInstalls(dependencies[pkg], result);
    }
  }
  return result;
}
```

### Big O

#### Time Complexity

This algorithm will have a runtime of `O(V + E)` where `V` is the number of packages to install, and `E` is the number of dependencies. This is a classic graph traversal problem of vertices (packages) and edges (dependencies).

`V` and `E` must both be included here because they represent different input sizes of the problem. `V` represents the number of `packages` in the initial function call (of which we loop over - `O(V)`). Each subsequent recursive call the the function will also loop over a list of packages, but the size of this list varies; it is the length of how many dependencies each initial package has. The set of all dependencies is `E`.

_NOTE: this time complexity can only be achieved if removing duplicates from the `result` is done in `O(1)` time (ie: using a hash table). Other approaches (ie: `.includes()`) will add a nested `O(V)` step, leaving the final time complexity to be `O(V^2 + E)`._

#### Space Complexity

Space used in the optimal time complexity solution is `O(V)` where `V` is the number of packages to install.

_NOTE: `O(1)` space complexity can be achieved through a tradeoff with time complexity: replacing the `O(1)` duplicate check with a `O(V)` suplicate check will yield `O(1)` space complexity._

### Notes

* Strongly guide students to approach this problem recursively, not iteratively.
* Remind students that the `dependencies` are an adjacency list, guiding them towards recognizing this is a graph problem.
* Offer them a sample `dependencies` adj list if they are struggling to get started.
* Be sure to clarify that their understanding of the input/output is clear before diving into the approach (feel free to offer examples, or ask questions expanding on their examples)
