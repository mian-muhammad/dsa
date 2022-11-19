---
title: "What is Linear Search?"
description: "Introduction to Linear Search Algorithm."
---

# Linear Search Algorithm explanation.

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
