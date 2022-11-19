---
title: "What is Binary Search?"
description: "Introduction to Binary Search Algorithm."
---

# Binary Search Algorithm explanation.

In computer science, binary search, also known as half-interval search, logarithmic search, or binary chop, is a search algorithm that finds the position of a target value within a sorted array. Binary search compares the target value to the middle element of the array; if they are unequal, the half in which the target cannot lie is eliminated and the search continues on the remaining half until it is successful. If the search ends with the remaining half being empty, the target is not in the array.

## Time Complexity

`O(log(n))` - Since we split search area by two for every next iteration.

## Space Complexity

## Implementation

```typescript
export default function bs_list(haystack: number[], needle: number): boolean {
  let lo = 0;
  let hi = haystack.length;

  do {
    const m = Math.floor(lo + (hi - lo) / 2);
    const v = haystack[m];

    if (v === needle) {
      return true;
    } else if (v > needle) {
      hi = m;
    } else {
      lo = m + 1;
    }
  } while (lo < hi);

  return false;
}
```

```typescript
export default function binarySearchRecursive(
  array: number[],
  x: number,
  left: number,
  right: number
): boolean {
  if (left > right) return false;

  mid = Math.floor(left + (right - left) / 2);

  if (array[mid] == x) {
    return true;
  } else if (x < array[mid]) {
    return binarySearchRecursive(array, x, left, mid - 1);
  } else {
    return binarySearchRecursive(array, x, mid + 1, right);
  }
}
```

```typescript
export default function binarySearchIterative(
  array: number[],
  x: number
): boolean {
  left = 0;
  right = array.length - 1;

  while (left <= right) {
    mid = Math.floor(left + (right - left) / 2);

    if (array[mid] == x) {
      return true;
    } else if (x < array[mid]) {
      right = mid - 1;
    } else {
      left = mid + 1;
    }
  }

  return false;
}
```
