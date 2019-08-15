# Data Structures
## List
Lists are the array of MATLAB, but can store different type of information, including list of lists.

* Index begin with `0`
* **Call an element** using `my_list[index]`
* **Concatenate** lists using `+`
* **Insert new element** in position `i` using `listName.insert(i, element)`
* **Quick list creation** -> called *List Comprehension* 
```py
evens_to_50 = [i for i in range(51) if i % 2 == 0]
other_list = [[i,j] for i in range(x) for j in range(y) if (x+y)!=n]
```

To call multiplex index
```py
my_list[:2] # Grabs the first two items
my_list[3:] # Grabs the fourth through last items
my_list[::2] # The stride is set to 1 by default
# in general we have
[start:end:stride]
```
** The first number is *insclusive*, the second number is *exclusive*.** A *negative stride* progress through the list from right to left.

Lists can be multi-index, call using `my_list[index1][index2]`.

### List Manupulation
Add an element to a list using
```py
listName.append(newElement)
```

Return the number of elements of the list using
```py
len(listName)
```

Return the index of the first element equal to `value`
```py
listName.index(value)
```

Insert the element `value` with the `index` position and moves everything down by 1
```py
listName.insert(position, value)
```

Return the same list sorted
```py
listName.sort()
```

Remove an element from the list
```py
listName.remove(value)
```

Remove the item at `index` from the list and return it
```py
listName.pop(index)
```
- - - -
## Dictionary
- - - -
## String
* Split a string using `stringVar.split()`
- - - -
## Tuples
[doc](https://docs.python.org/3.3/tutorial/datastructures.html#tuples-and-sequences)
Number of values divided by commas, like
```py
t = 12345, 54321, 'hello!'
# Tuples may be nested:
u = t, (1, 2, 3, 4, 5)
# Empty tuple and 1-element tuple
empty = ()
single = ('hello',)
```
* Tuples are **immutable**.  They usually contain an heterogeneous sequence of elements that are accessed via *unpacking* or *indexing*.
* Tuples can be *unpacked* using
```py
x, y, z = t
```
- - - -
#code/python/tips