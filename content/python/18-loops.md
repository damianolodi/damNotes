# Loops and Conditionals
## Loops
### `For` loop
The `for` loop iterate through all the elements of a list
```py
a = [1, 2, ’hi’]
for var in a:
    #...
else:
    #...
```
The `else` condition will be executed at the end of the loop, but not if one exit with `break`.

One can use `for` also on a string or on a dictionary
```py
#a simple dictionary
d = {"foo" : "bar"}
for key in d:
    print d[key] #prints "bar"
```
*Note that dictionaries are **unordered**, meaning that any time you loop through a dictionary, you will go through every key, but you are not guaranteed to get them in any particular order.*

`enumerate` supply a corresponding index to each element in the list that you pass it
```py
for index, item in enumerate(listName):
    print index , item
```

One can iterate over two (or multiple) lists at once. `zip` will create pairs of elements when passed two lists, and will stop at the end of the shorter list.
```py
list_a = [3, 9, 17, 15, 19]
list_b = [2, 4, 8, 10, 30, 40, 50, 60, 70, 80, 90]
for a, b in zip(list_a , list_b):
    #...
```

### `While` loop
```py
while condition:
    #...
else:
    #...
```
The `else` block will execute anytime the loop condition is evaluated to `False`. It is not executed when exiting using `break`.

## Conditionals
We have 6 comparators...
* equal to `==`
* not equal to `!=`
* less than `<`
* less than or equal to `<=`
* greater than `>`
* greater than or equal to `>=`

... and 3 boolean operators ...
* `not` is evaluated first
* `and` is evaluated next
* `or` is evaluated last

Finally we have the `if` statement
```py
if 8<9 :
    # do something
elif 8>9:
    #do something
else:
    # do something else
```

- - - -
#code/python/tips