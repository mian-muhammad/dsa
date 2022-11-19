---
title: "What is Linear Search?"
description: "Introduction to Linear Search Algorithm."
---

# Linear Search Algorithm explanation.

In computer science, linear search or sequential search is a method for finding a target value within a list. It sequentially checks each element of the list for the target value until a match is found or until all the elements have been searched. Linear search runs in at worst linear time and makes at most n comparisons, where n is the length of the list.

## Time Complexity

`O(n)`

## Space Complexity

## Implementation

```typescript
export default function linear_search(
  haystack: number[],
  needle: number
): boolean {
  for (let i = 0; i < haystack.length; ++i) {
    if (haystack[i] === needle) {
      return true;
    }
  }

  return false;
}
```
