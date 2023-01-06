# Max Profit

Time: 30 minutes

### Prompt

#### Problem Statement

You are given an array where each `i`th element is the price of a given stock on day `i`. If you were only permitted to complete at most one transaction (i.e., buy one and sell one share of the stock), write a function `maxProfit` to find the maximum profit. Note that you cannot sell a stock before you buy one.

#### Sample Input/Output:

Example 1:
```js
maxProfit([7, 1, 5, 3, 6, 4]); // 5
// buy at 1, sell at 6
```

Example 2:
```js
maxProfit([7, 6, 4, 3, 1]); // 0
// no transaction
```

### Solution

```js
const maxProfit = (arr) => {
  let currMinIdx = 0;
  let profit = 0;

  for(let i = 1; i < arr.length; i++) {

    // new current min
    if(arr[i] < arr[currMinIdx]) {
      currMinIdx = i;
    }

    // new best profit
    let currentProfit = arr[i] - arr[currMinIdx];
    profit = Math.max(profit, currentProfit);
  }

  return profit;
}
```

This is the optimized solution, which requires 1 loop. It keeps track of local mins, updating `profit` each time a better potential sale price is found.

The brute force approach to this problem usually involves a nested loop to compare each possible buy price against each possible sell price.

### Big O

#### Time Complexity

The optimized solution has a runtime of `O(n)`.

The brute force approach is `O(n^2)`.

#### Space Complexity

This algorithm uses `O(1)` space.

### Notes

Most students can figure out the brute force relatively quickly, so guide these students towards figuring out the optimized solution.
