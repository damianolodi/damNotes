---
title: "stdlib.c"
draft: false
arguments: [""]
weight: 6
---

vedi malloc(memoryAmount) [allocate memory]

e.g. malloc(strlen(s)+1 \* sizeof(char))

free(pointerName) [deallocate memory]

If memory is not deallocated, program can cause memory leaks.
!! Always free memory allocated with malloc!!

-   **Segmentation fault**: error caused by the fact that I try to access to memory that I should not use.

-   When allocating memory, PCs usually allocate a little bit more to avoid problems.

realloc() reallocate memory in the (heap part) if available. $O(n)$ in term of efficency

### Memory Allocation
