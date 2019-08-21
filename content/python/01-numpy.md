---
title: "NumPy"
draft: false
arguments: ["Array Generation",
            "Array Methods",
            "File I/O",
            "Data Analysis"]
---

```py
import numpy as np

array[index1, index2] # access an element. Use : to access the all line
array[start:stop:stride] # array slicing
np.nditer(array) # create an iterator object to be used in for loops

# Array generation
np.array(list) # create array from list
np.arange(first, size, spacing) # generate array
np.linspace(first, last, size) # generate array, both end points are included
np.logspace(first, last, size, base=e) # generate log-spaced array
np.zeros((dim1,dim2)) # create array full of 0s
np.ones((dim1,dim2)) # create array full of 1s
```

Numpy arrays are statically typed and homogeneous. The type of the elements is determined when the array is created.

-   Jupyter notebook [tutorial](http://nbviewer.jupyter.org/github/jrjohansson/scientific-python-lectures/blob/master/Lecture-2-Numpy.ipynb) on **numpy**

* * *

### Arrays Methods

-   `np.shape(array)` → return array **dimensions** (tuple)

-   `np.size(array)` → return **number of elements**

-   `np.ndim(array)` → return **number of dimensions**

-   `np.dtype(list)` → return the **data type** of the array

-   `np.random.rand(d0,d1,...)` → generate a `d0, d1,…` dimension array made of **uniformly distributed random numbers** between 0 and 1

-   `np.random.randn(d0,d1,...)` → generate a `d0, d1,…` dimension array made of **gaussian distributed random numbers** between 0 and 1

-   `np.random.permutation(array)` → shuffle the array (or pandas Series)

* * *

### File I/O from Arrays

-   `data = np.genfromtxt('csv-or-tsv-file.dat')` → **import data** from file

-   `savetxt('file-name.csv', array-name, fmt='%.5f')` → **save the array** in a cvs file and specify the format (optional)

-   `np.save(‘file-name.npy’,array-name)` → save array in a _proprietary file format_

-   `np.load(‘file-name.npy’)` → load array from _proprietary file format_

* * *

### Data Analysis

-   `mean(array)` → compute the _mean_ of the array

-   `std(array)` → compute _standard deviation_

-   `var(array)` → compute _variance_

-   `array.min()`, `array.max()` → find _min_ and _max_ values

-   `sum(array)`, `cumsum(array)` → compute _sum_ and _cumulative sum_

-   `prod(array)`, `cumprod(array)` → compute _product_ and _cumulative product_

-   `np.dot(a,b)` → **dot product** of 2 arrays/matrices [doc](https://docs.scipy.org/doc/numpy/reference/generated/numpy.dot.html#numpy.dot)
