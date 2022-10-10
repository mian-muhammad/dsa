---
title: "What is quicksort?"
description: "Introduction quicksort Algorithm."
---

# Quicksort Algorithm explanation.

Quicksort is a recursive sorting algorithm. In this algorithm, the hard work is splitting the array into smaller sub arrays before _recursion_, so that merging the sorted sub arrays is trivial.

1. Choose a _pivot_ element from the array.
2. Partition the array into three sub arrays containing the elements smaller than or equal to the _pivot_, the _pivot_ element itself, and the elements larger than _pivot_.
3. Recursively quicksort the first and last sub arrays.

## Time Complexity

1. Best - Ω(n log(n))
2. Average - Θ(n log(n))
3. Worst - O(n<sup>2</sup>)

## Space Complexity

- Worst - O(log(n))

## Implementation

```javascript
function quickSort(nums) {
  if (nums.length <= 1) return nums;

  const pivot = nums[nums.length - 1];

  const left = [];
  const right = [];

  for (let i = 0; i < nums.length - 1; i++) {
    if (nums[i] < pivot) {
      left.push(nums[i]);
    } else {
      right.push(nums[i]);
    }
  }

  quickSort(left);
  quickSort(right);

  return [...quickSort(left), pivot, ...quickSort(right)];
}
```
