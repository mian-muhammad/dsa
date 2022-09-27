---
title: "Measuring Algorithmic Complexity."
description: "The introduction to this course."
---

# Algorithmic Complexity

To calculate the complexity of an algorithm we just need to count the number of statements our program has to execute.

```javascript
function askInfo() {
  console.log("Enter your name:");
  console.log("Enter your name:");
  console.log("Enter your name:");
  console.log("Enter your name:");
}
```

Here is how time complexity is calculated:

- Statement count = 4
- Complexity = O(4)
- Constant Complexity = O(1)

Here is an example where complexity depends on given input.

```javascript
function printItems(items) {
  for (let i = 0; i <= items.length; i++) {
    // do something
  }
}
```

The statement count is `1 + 4n`, since `n` has the highest significance, we can drop the constants.

- Statement count = `1 + 4n`
- Complexity = `O(4n)`
- Constant Complexity = `O(n)`

## Common Complexities

Here is the list of common complexities

1. Linear - O(n)
2. Quadratic - O(n<sup>2</sup>)
3. Constant - O(1)
4. Exponential - O(log n)
