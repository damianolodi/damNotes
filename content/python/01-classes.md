---
title: "Classes"
draft: false
---

Classes are used to define objects in python. Every object has **properties** and associated **methods** (functons).

* * *

### Class Definition

```python
class Person:
    def __init__(self, name, age): #(self, var1, var2)
        self.name = name #self.property_name = var1
        self.age = age

    def my_func(self):
        print("Hello my name is " + self.name)
```

-   The `__init__()` is needed in all classes definition and it is always executed when the class is being initiated. It is used to **assign values to object properties,** or other operations that are necessary to do when the object is being created.

-   The function `my_func` is a method of the class.

-   For convention, class names start with **capital letters.**

**Use** `self.property_name` **to access properties values inside the class definition.** The `self` parameter is a reference to the current instance of the class.

* * *

### Object Creation

-   `new_object = My_class(property_name1, property_name2, ...)` → **create** an object

-   `new_object.property_name1` → **access a property**

-   `new_object.property_name1 = new_value` → **modify a property**

-   `new_object.method()` → **apply a method**

-   `del new_object.property_name1` → **delete** an object property

* * *

### Inheritance

Inheritance allows one to define a class that inherits (acquire) all the methods and properties from another class. Then one has a **parent class** and a **child class.**

To **define** a new _child class_ use

```python
class Student(Person):
    def __init__(self, fname, lname, year):
        #add properties etc.
        self.graduationyear = year

    def welcome(self):
        print("Welcome", self.firstname, self.lastname, "to the class of", self.graduationyear)
```

-   When one adds the `__init__()` function, the _child class_ will **no longer inherit** the parent's `__init__()` function. To keep the inheritance of the parent's `__init__()` function, add a call to the parent's `__init__()` function:

```python
    class Student(Person):
        def __init__(self, fname, lname, year):
            Person.__init__(self, fname, lname)
            self.graduationyear = year

        def welcome(self):
            print("Welcome", self.firstname, self.lastname, "to the class of", self.graduationyear)
```

-   If one adds a method in the _child class_ with the **same name** as a function in the parent class, _the inheritance of the parent method will be overridden._

```python
    class Person:
        def __init__(self, name, age):  # (self, var1, var2)
            self.name = name  # self.property_name = var1
            self.age = age

        def my_func(self):
            print("Hello my name is " + self.name)
```
