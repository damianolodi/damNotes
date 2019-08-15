---
title: "Core"
draft: false
---

### Lists

-   `l = [100, 21, 88, 3]` → **initialize** the list

-   `l = list()` → create empty list

-   `len(list)` → return the **length** of the list

#### Manupulation

-   `l.append(item)` → **add** a new item at the end of the list

-   `min(list); max(list)` → return **min** or **max** value of the list

-   `list.sort()` → **sort** in ascendin order

-   `" ".join(["A","B","C","D"])` → **combine list elements** into the string "A B C D"

#### Searching

-   `item in list` → return a boolean if item is found in list

* * *

### Strings

-   `len(string)` → **lenght** of the string

#### Searching

-   `string.find("substring", start, stop)` → **search** substring in string and return the lowest index where it is found. Return -1 instead.

-   `string.startswith("something")` → check if **string starts** with "something".

-   `string.endswith("something")`→ check if **string ends** with "something".

#### Manipulate

-   `string.split('delimiter')` → **split** a string using _delimiter_. Return a list.

-   `'string {0} something {1}'.format(34,'something_else')` → **format the string** replacing `{ }` with arguments ([doc](https://docs.python.org/3.1/library/stdtypes.html?highlight=format#str.format)).

-   `string.replace('e','z')` → **replace** all "e" with "z".

-   `zip(a,b,...)` → make an **iterator** that aggregates elements from each of the iterables ([doc](https://docs.python.org/3.3/library/functions.html?highlight=zip#zip)).

* * *

### Dictionaries

-   `d = {"CA":"Canada","GB":"Great Britain", "IN":"India"}` → initialize a dictionary with keys and corresponding values

-   `d["key"]` → return the value associated with the key "key"

-   `d.keys()` → return a list of the keys

-   `d.values()` → return a list of the values

-   `d.items()` → return a list of (key, value) pairs

#### Searching

-   `d.get("AU","Sorry")` → Return the value from the dictionary d that has the key "AU", or the string "Sorry" if the key "AU" is not found in d

-   `"key" in d` → Checks whether the "key" exists in d

* * *

### Functions

-   Define a new function using

```python
    def func_name(var1, var2, var3=default_value):
        <code>
        return something1, something2, ...
```

* * *

### Loops and Conditionals

#### `If` statement

```python
if condition1:
    <code>
elif condition2:
    <code>
else:
    <code>
```

#### `For` loops

```python
for item in list:
    <code>
```

#### `While` loops

```python
while condition:
    <code>
```
