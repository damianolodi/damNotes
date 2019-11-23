---
title: "Basic Concepts"
draft: false
arguments: ["Basics",
            "Variable Types",
            "Loops and Conditionals",
            "Functions",
            "Pointers",
            "Data Structures",
            "Compiler Workflow",
            "Tips"]
weight: 1
---

### Basics

```c
int var_name = value;           // variable initialization
char str_name[n];               // array initialization
char str_name[] = "Hello World!";
const int VAR_NAME = value;     // constant declaration

int main (void) {               // execution start from here
    // code
    return 0;
}
```

-   **Best practice**: variables are named with capital letters when global

-   **Math operators** &rarr; `+`, `-`, `*`, `/`, `%` (mod)

-   For each string of _n_ charachters, _n+1_ bytes are allocated in memory: the last is added by C as the _null_ character `\0` (all zeros)

-   `(type) var_name` &rarr; change variable type

-   `man function_name` &rarr; use in terminal to return documentation about the function

#### `main` with External Parameters

```c
int main (int argc, char* argv[]) {
}
```

-   Enable the program to **accept parameter from the command line** when run

-   `argc` &rarr; number of written words, _including_ the name of the program. This value is auto-generated

-   `argv[]` &rarr; array of strings. `argv[1]` is the location of the first parameter inserted by the user

#### Compilation

-   `clang file.c` &rarr; compile and produce `a.out`

-   `clang -0 file file.c` &rarr; compile and produce `file`

-   `make file.c` &rarr; call clang to compile (elaborate on that)

* * *

### Variables Type

-   **Arrays**
    -   fixed size
    -   cannot contain mixed data types

* * *

### Loops and Conditionals

#### If Statement

```c
if (condition) {
} else {
}
```

-   `==`, `!=`, `>`, `<`, `>=`, `<=` &rarr; comparators
-   **not**, **and**, **or** &rarr; boolean operators

#### For Loop

```c
for (initialization; condition; last step) {
}
```

#### While Loop

```c
while (condition) {
}

do {
} while (condition);
```

* * *

### Functions

```c
// before main
int function_name (parameters); // PROTOTYPE

// after main
int function_name (parameters) { // DEFINITION
    // code
}
```

* * *

### Pointers

```c
int* pointer_name; // pointer declaration

// return the value pointed by that pointer
var = *pointer_name;

// return the address of the variable
pointer = &var_name;
```

-   **DEF**: memory addres of a variable of a certain type

-   Pointers are 64 bits in lenght

* * *

### Data Structures

```c
// structure definition
typedef struct {
    int var1;
    char var2;
} struct_name;

// structure initialization
struct_name var_name;
struct_name var_name[n]; // array of structure

// access with dot notation
var_name.var1 = value;
```

-   save in a `file.h`
-   import with `#include`

#### Recursive Structures

```c
typedef struct struct_name {
    int n;
    struct struct_name *next; // pointer to my structure
} struct_name;
```

-   `struct_name` is called also before definition so that the compiler knows that a structure called `struct_name` exists

-   this sort of structure can be usefull to create a "linked list" in which I store a value and the pointer to the next value in the list
    -   the last element of the list will point to NULL
    -   this solve the fact that arrays are fixed size in C, but it has the downside that when parsing the list I always have to begin from the start and I cannot go backward
    -   if I don't care about sorting, this is an O(1) in terms of adding elements to the list (against O(n) when using `malloc`) but I am "wasting" memory to store all those pointers

<img src="/img/content/c/linked-list.jpg" class="img-fluid figure-img img-custom">

* * *

### Compiler Workflow

1.  **Preprocessing**
    -   `#include` are called _preprocessor directives_
    -   `#` means that it should be handeled first, before everything else
2.  **Compiling**
    -   Code is translated into _assembly language_, understood by CPUs
3.  **Assembling**
    -   _Assembly_ is translateed into 0s ans 1s
4.  **Linking**
    -   Also libraries are compiled in 0s and 1s, and all those files are linked/attached one another

* * *

### Tips

-   `echo $` &rarr; print what was returned by main. **Usefull to debug** complicated programs. Return a non-0 value if anything goes wrong
