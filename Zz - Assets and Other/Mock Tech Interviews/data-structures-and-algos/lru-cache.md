# Technical Mock Interview

## Overview


### Question 

#### LRU Cache (30 minutes)

Implement an LRU Cache that can only hold 100 items and after it reaches 100 items, it follows the least recently used eviction policy. The LRU Cache should implement these classes:

- A Node Class that has a next and prev value (can be given)
- A Cache Class that implements these methods:
  - `setHead(node)` which helps mark the nodes as most recently used
  - `get(key)` which returns an item from the cache
  - `set(key, value)` which adds an item to the cache and overwrites the current entry if it exists and implements the LRU policy
  - `remove(key)` which removes an item from the cache
  - `clear` which resets the cache to an empty state (can be extra credit)

```js

let prompt = `Your code here`
```

#### Solution

```javascript
class Node {  
  constructor(key, value) {
    if (typeof key !== 'undefined' || typeof key !== null) {
      this.key = key
    }
    if (typeof value !== 'undefined' || typeof value !== null) {
      this.value = value
    }
    this.next = null
    this.prev = null
  }
}


class Cache {  
  constructor(limit = 100) {
    if (typeof limit === 'number') {
      this.limit = limit
    }
    this.size = 0
    this.lookup = {}
    this.head = null
    this.tail = null
  }
  
  /*
    Marks most recently used item
    Takes one argument
  */
  setHead(node) {
    node.next = this.head
    node.prev = null
    
    if (this.head !== null) {
      this.head.prev = node
    }
    this.head = node

    if (this.tail === null) {
      this.tail = node
    }
    this.size++
    this.lookup[node.key] = node
  }

  /*
   Retrieve an item from the cache and "marks" it as most recently used
   Takes one argument
  */
  get(key) {
    if (this.lookup[key]) {
      const value = this.lookup[key].value
      const node = new Node(key, value)
      this.remove(key)
      this.setHead(node)
      return value
    }
  }

  /*
    Add an item in the cache where it: 
    1. If a value already exists at the key, overwrite it
    2. If the cache is full, implement the LRU policy and marks the item and most recently used
    Takes 2 arguments
  */
  set(key, value) {
    const node = new Node(key, value)
    if (this.lookup[key]) {
      this.remove(key)
    } else {

      if (this.size >= this.limit) {
        delete this.lookup[this.tail]
        this.size--
        this.tail = this.tail.prev
        this.tail.next = null
      }
    }
    this.setHead(node)
  }

  /*
   Remove an item from the cache
   Takes a key argument
  */
  remove(key) {
    if(this.lookup[key]) {
      const node = this.lookup[key]
    
      if (node.prev !== null) {
        node.prev.next = node.next
      } else {
        this.head = node.next
      }
      
      if (node.next !== null) {
        node.next.prev = node.prev
      } else {
        this.tail = node.prev
      }

      delete this.lookup[key]
      this.size--
    }
  }

  /*
    Reset cache to an empty state.
    Takes no arguments.
  */
  clear() {
    this.size = 0
    this.lookup = {}
    this.head = null
    this.tail = null
  }
}
```

- Time Complexity: O(1)
- Space Complexity: O(n)


### Notes

A least recently used (LRU) cache discards the least recently used item when the cache becomes full. This requires keeping track of what was used when. This is what maintains the 0(1) lookup time.

When an item is read or added from the cache, it is marked as the most recently used item, and all other items get "shifted" over one. If full, the last item gets removed (shifted off). The key to this is using a doubly linked list to rearrange the elements, and a JavaScript object to store everything.

JavaScript objects act exactly as a hash table and provide O(1) lookup. We can use a "head" and "tail" node to maintain the oldest and newest items. Each key 
s to a node, which has the key and value, as well as a pointer to the next and previous nodes. 
