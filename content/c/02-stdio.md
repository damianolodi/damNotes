---
title: "stdio.c"
draft: false
arguments: ["Print to Console",
            "Request Input from User"]
weight: 2
---

```c
#include <stdio.h>
```

- `printf(` &rarr; Possible placeholders:
    
    - `%c` (single char), `%s` (string), 
    
    - `%i` (integer), `%f` (float), `%u` (unsigned decimal integer)

    - `%p` (pointer)

- `scanf("%i", &varName)` &rarr; **wait user input**. Various placeholders are available (number in different bases, strings,...). Return the number of characters written, or a negative number if some errors occured. **WARNING:** the input should be checked for correctness

