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
quicksort(arr: number[], low: number, high: number) {
  if(low < high) {
    const p = partition(arr,low,high);

    quick(arr, low, p - 1);
    quick(arr, p + 1, high);
  }
}

partition(arr: number[], a:number, b: number) {
  const pivot = arr[high];
  let i = low;

  for(let j = low; j < high; j++) {
    if(arr[j] < pivot) {
      swap(arr,i,j);
      i++
    }
  }
  swap(arr, i, high);
}

private swap(arr: number[], a: number, b: number) {
  const tmp = arr[a];
  arr[a] = arr[b];
  arr[b] = tmp;
}
```
