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

```typescript
function quickSort(nums: number[]) {
  if (nums.length <= 1) return nums;

  const pivot: number = nums[nums.length - 1];

  const left: number[] = [];
  const right: number[] = [];

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

In place implementation of Quick Sort

```typescript
const array = [1, 2, 33, 31, 1, 2, 63, 123, 6, 32, 943, 346, 24];

/**
 * Split array and swap values
 *
 * @param {Array<number>} array
 * @param {number} [left=0]
 * @param {number} [right=array.length - 1]
 * @returns {number}
 */
function partition(
  array: Array<number>,
  left: number = 0,
  right: number = array.length - 1
) {
  const pivot = array[Math.floor((right + left) / 2)];
  let i = left;
  let j = right;

  while (i <= j) {
    while (array[i] < pivot) {
      i++;
    }

    while (array[j] > pivot) {
      j--;
    }

    if (i <= j) {
      [array[i], array[j]] = [array[j], array[i]];
      i++;
      j--;
    }
  }

  return i;
}

/**
 * Quicksort implementation
 *
 * @param {Array<number>} array
 * @param {number} [left=0]
 * @param {number} [right=array.length - 1]
 * @returns {Array<number>}
 */
function quickSort(
  array: Array<number>,
  left: number = 0,
  right: number = array.length - 1
) {
  let index;

  if (array.length > 1) {
    index = partition(array, left, right);

    if (left < index - 1) {
      quickSort(array, left, index - 1);
    }

    if (index < right) {
      quickSort(array, index, right);
    }
  }

  return array;
}

console.assert(
  quickSort(array, 0, array.length - 1).toString() ===
    "1,1,2,2,6,24,31,32,33,63,123,346,943",
  "Wrong Implementation"
);
```
