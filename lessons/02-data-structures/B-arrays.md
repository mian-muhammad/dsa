---
title: "What are Arrays?"
description: "An Introduction to Arrays."
---

# What are arrays?

Arrays are collection of items stored consecutively in the memory. Each character is placed to next item in array
Two characters to keep in mind.

- Items have the same type.
- Fixed in size.

```cpp
int numbers[3] = {10, 19, 11};
string cars[3] = {"BMW", "Volvo", "Ford"};
char types[3] = {'A', 'G', 'U'};
```

Arrays are fixed in size so can't allocate space at the run time.

Arrays cannot have mixed types

```cpp
number[4] = 594; // not allowed!
mixed[3] = {'A' , "BMW", 59}; // not allowed!
```

Why do have these limitations? Lets we have an array of integer which have to represent in memory.

```cpp
int numbers[3] = {10, 59, 11};
```

What program will do is it is going to allocate three slots in memory.

```cpp
int numbers[3] = {10, 59, 11};
bool states[2] = {false, true};
char types[3] = {'A', 'G', U'};
```

Memory allocation:

- int - 2 Bytes Each
- bool - 1 Byte Each
- char - 1 Byte Each

How some languages have the capability to have mixed type arrays.

- memory capping
- boxing the size

## Array Operations(Algorithmic Complexities)

- Read - O(1)
- Insert - O(n)
- Delete - O(n)
- Update - O(1)
- Traverse - O(n)
