---
title: "stdlib.c"
draft: false
arguments: ["Memory Allocation"]
weight: 6
---

```c
#include <stdlib.h>
```

- `malloc(size)` &rarr; try to allocate requested memory size (in bytes) and returns a pointer to the first byte

```c
    // allocate space for 4 integer numbers
    int *p = malloc(4 * sizeof(int));
```
    
    - **Segmentation fault**: error caused by the fact that the program is trying to access memory that it should not use

    - When allocating memory, PCs usually allocate a little bit more to avoid problems

- `free(pointName)` &rarr; **deallocate memory** previously allocated with `malloc`. **WARNING:** always free memory allocated with malloc. If memory is not deallocated, program can cause memory leaks.

- `realloc()` &rarr; try to **reallocate memory** in the heap part, if available. It is an _O(n)_ in term of efficency

```c
    str = realloc(str, 5 * sizeof(char));
```
