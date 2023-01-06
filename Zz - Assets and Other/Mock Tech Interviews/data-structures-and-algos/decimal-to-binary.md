# Technical Mock Interview

## Overview

Implement a function that converts decimal to binary.

### Question 

#### Decimal to Binary (20 mins)

Implement a function that a base 10 (decimal) integer, and return the string representation of that value in base 2 (binary).

```javascript


decimalToBinary(4); // should return '100'
decimalToBinary(67); // should return '1000011'

```


#### Solution



```javascript

function decimalToBinary(num) {
    let binaryStr = '';
    while(num) {
        let remainder = num % 2;
        binaryStr = remainder + binaryStr;
        num = (num - remainder)/2;
    }
    return binaryStr;
}
```

Or we could use some fancy bit logic that should ultimately be more performant (constant space).

```javascript
function decimalToBinary (num) {
    const bits = [];
    while (num !== 0) {
        bits.push(num & 1);
        num >>= 1;
    }
    return bits.reverse().join('');
}

```

### Notes

Good sub-question:

* How do we convert binary values to decimal? 
* Can we write a function that converts binary to decimal
* What are bitwise operators? How do they work?