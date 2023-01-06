# Technical Mock Interview

## Overview

Given an array of elements, return the array in a randomized order

### Question 

#### Shuffle Array (20 mins)

Given an array of 'cards', create a function which returns the same array in a "shuffled" order;


```js

let deck = [2,3,4,5,6,7,8,9,10,'J','Q','K','A'];

const shuffle = cards => {...}
```


#### Solution


```js

const swap = (cards, idx) => {
	let randomIdx = Math.floor(Math.random() * cards.length);
	let placeholder = cards[idx];
	cards[idx] = cards[randomIdx];
	cards[randomIdx] = placeholder; 
}

const shuffle = cards => {
	cards.forEach((card, idx) => {
		swap(cards, idx)
	})
	return cards;
}

```


### Notes

Good sub-questions to ask:

* What if we want to return a new array?
* What is in-place mutation? Does JS allow it?
* How can we implement this recursively?

