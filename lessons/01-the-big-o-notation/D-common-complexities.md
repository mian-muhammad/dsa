---
title: "Common Algorithmic Complexities"
description: "The introduction to this course."
---

## Algorithmic Complexity

Here is the list of common complexities

1. Linear - O(n)
2. Quadratic - O(n<sup>2</sup>)
3. Constant - O(1)
4. Exponential - O(log n)

## Linear - O(n)

In Linear algorithmic complexity with increase in number of inputs, space/time taken will grow linearly.

```javascript
for (let i = 0; i <= n; i++) {
  // do something
}
```

## Quadratic - O(n<sup>2</sup>)

In Quadratic algorithmic complexity time and space taken squares with each increase in the number of inputs.

```javascript
for (let i = 0; i <= n; i++) {
  for (let j = 0; j <= n; j++) {
    // do something
  }
}
```

## Constant - O(1)

In Constant algorithmic complexity no matter what the input size is, time and space always remain the same.

```javascript
let names = ["John Doe", "Jane Doe", "Alex"];
console.log(name[0]);
```

## Exponential - O(log n)

In Exponential algorithmic complexity with increase in number of inputs there is exponential growth in time or space.

```javascript
function fibonacci(n) {
  if (n <= 1) return n;
  return fibonacci(n - 2) + fibonacci(n - 1);
}
```

![comparison of different time complexities](./images/comparison.png)
