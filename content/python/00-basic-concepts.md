---
title: "Basic Concepts"
draft: false
arguments: ["Variable Types",
            "Loops and Conditionals",
            "Functions",
            "Lambda Function",
            "Classes",
            "Virtual Environments"]
weight: 1
---

### Variable Types

#### Lists

```py
l = [100, 21, 88, 3]
l = list() #empty list

# List Comprehension -> quick list creation
evens_to_50 = [i for i in range(51) if i % 2 == 0]
other_list = [[i,j] for i in range(x) for j in range(y) if (x+y)!=n]

# Element selection
l[:2] # first two items (0 and 1)
l[3:] # ourth through last items
l[::2] # first through end with a step of 2
## in general [start(inclusive):end(exclusive):stride]
## negative stride progress the list in reverse order

# Multi-index lists
l = [0, 1, 2, 3;
     4, 5, 6, 7]
l[1][2] #6
```

-   `l1 + l2` → **concatenate** lists

-   `len(list)` → **length** of the list

-   `min(list)`, `max(list)` → return **min** or **max** value of the list

-   `l.append(item)` → **add** _item_ at the end of the list

-   `l.insert(i, value)` → **insert** _new value_ in position _i_

-   `l.pop(index)` → **remove** item at _index_

-   `list.sort()` → **sort** in ascending order

-   `item in list` → return a boolean if _item_ **is found** in _list_

-   `l.index(value)` → return **first index** in which _value_ is found

#### Strings

```py
s = "Ciao!"
```

-   `len(string)` → **lenght** of the string

-   `" ".join(["A","B","C","D"])` → **combine list elements** into the string "A B C D"

-   `s.find("substring", start, stop)` → **search** substring in string and return the lowest index where it is found. Return -1 instead.

-   `s.startswith("something")` → check if _string_ **starts** with "something".

-   `s.endswith("something")`→ check if _string_ **ends** with "something".

-   `s.split('delimiter')` → **split** a string using _delimiter_. Return a list.

-   `s.replace('e','z')` → **replace** all "e" with "z"

-   `'string {0} something {1}'.format(34,'something_else')` → **format the string** replacing `{ }` with arguments ([doc](https://docs.python.org/3.1/library/stdtypes.html?highlight=format#str.format))

-   `zip(a,b,...)` → make an **iterator** that aggregates elements from each of the iterables ([doc](https://docs.python.org/3.3/library/functions.html?highlight=zip#zip))

#### Dictionaries

```py
d = { "CA":"Canada",
      "GB":"Great Britain",
      "IN":"India",
      "key": value}
```

-   `d["key"]` → return the value associated with the key "key"

-   `d.keys()` → return a list of the keys

-   `d.values()` → return a list of the values

-   `d.items()` → return a list of _(key, value)_ pairs

-   `d.get("AU", "Sorry")` → return the value from the dictionary d that has the key "AU", or the string "Sorry" if the key "AU" is not found in d

-   `"key" in d` → checks if _key_ exists in _d_

#### Tuples (sistema)

[doc](https://docs.python.org/3.3/tutorial/datastructures.html#tuples-and-sequences)
Number of values divided by commas, like

```py
t = 12345, 54321, 'hello!'
u = t, (1, 2, 3, 4, 5) # nested tuples
empty = () # empty tuple
single = ('hello',) # 1-element tuple
```

-   **immutable** → tuples usually contain an heterogeneous sequence of elements that are accessed via _unpacking_ or _indexing_

```py
    x, y, z = t # unpacking tuples
```

* * *

### Loops and Conditionals

#### If Statement

```python
# if statement
if condition1:
    <code>
elif condition2:
    <code>
else:
    <code>
```

-   `==`, `!=`, `>`, `<`, `>=`, `<=` → comparators
-   **not**, **and**, **or** → boolean operators

#### For Loop

```py
for item in listName:
    <code>

for index, item in enumerate(listName):
    print index, item

list_a = [3, 9, 17, 15, 19]
list_b = [2, 4, 8, 10, 30, 40, 50, 60, 70, 80, 90]
for a, b in zip(list_a , list_b): # loop on multiple lists
    <code>
```

-   can loop also on _dictionaries_ and _strings_
-   dictionaries are **unordered**: the loop wil go through _every key_, but **not necessarily in the same order**
-   `zip()`→ stops at the end of the shorter list

#### While Loop

```py
while condition:
    <code>
else:
    <code>
```

-   `else` → executed enytime the _condition_ is evaluated as _False_
    -   **not executed** if the cycle is interrupted by `break`

* * *

### Functions

```python
def func_name(var1, var2, var3=default_value):
    <code>
    return something1, something2, ...
```

-   **recursion** is allowed

* * *

### Lambda Functions (sistema)

Small anonymous functions can be created with the [lambda](https://docs.python.org/2/reference/expressions.html#lambda) keyword.
This function returns the sum of its two arguments

```py
lambda a, b: a+b

lambda val: val > 1000000
```

-   **Lambda functions can be used wherever function objects are required.**
    They are syntactically restricted to a single expression. Semantically, they are just syntactic sugar for a normal function definition.
    Like nested function definitions, lambda functions can reference variables from the containing scope

* * *

### Classes

Classes are used to define **objects** in python. Every object has **properties** and associated **methods** (functons).

#### Class definition

```python
class Person:
    def __init__(self, name, age): #(self, var1, var2)
        self.name = name #self.property_name = var1
        self.age = age

    def my_func(self):
        print("Hello my name is " + self.name)
```

-   `__init__()` is **needed in all classes definitions**

    -   it is always executed when the class is initialized
    -   it is used to **assign values to object properties**, or to execute operations that are necessary to do when the object is being created

-   `my_func` is a **method** of the class

-   class names start with **capital letters** (convention)

-   `self.property_name` → **access properties values** inside the class definition

    -   the `self` parameter is a reference to the current instance of the class

#### Class manipulation

-   `new_object = My_class(property_name1, property_name2, ...)` → **create** an object

-   `new_object.property_name1` → **access** a property

-   `new_object.property_name1 = new_value` → **modify** a property

-   `new_object.method()` → **apply** a method

-   `del new_object.property_name1` → **delete** an object property

#### Inheritance

Inheritance allows one to define a class that acquire all the methods and properties from another class.

The new class is called **child class**, while the one from properties are inherited is called **parent class**.

```python
class Student(Person): # child class definition
    def __init__(self, fname, lname, year):
        #add properties etc.
        self.graduationyear = year

    def welcome(self):
        print("Welcome", self.fname, self.lname, "to the class of", self.graduationyear)
```

-   when `__init__()` is added, the _child class_ will **no longer inherit** the parent's `__init__()` function
-   to keep the inheritance of the parent's `__init__()` function, add a call to the parent's `__init__()` function

```python
    class Student(Person):
        def __init__(self, fname, lname, year):
            Person.__init__(self, fname, lname)
            self.graduationyear = year

        def welcome(self):
            print("Welcome", self.fname, self.lname, "to the class of", self.graduationyear)
```

-   if a new method in the _child class_ is defined with the **same name** as a function in the parent class, _the parent method will be overridden_

* * *

### Virtual Environments

-   install `virtualenv`

-   `cd` into the project folder

-   `conda create --name project-name-env dependecy1 dependency2 ...` → **create** the environment

-   `source activate project-name-env` → **activate** the environment

-   `source deactivate project-name-env` → **deactivate** the environment

-   `conda env export > environment.yaml` → **export** the environment

    -   keep track of all the dependencies

    -   have the possibility to reproduce the environment if something goes wrong

-   `conda env create -f environment.yaml` → create a virtual environment from a _.yaml_ file

-   `conda env list` → list all the environments on the machine with their location