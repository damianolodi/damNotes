---
title: "NumPy"
draft: false
---

**See** [here](http://nbviewer.jupyter.org/github/jrjohansson/scientific-python-lectures/blob/master/Lecture-2-Numpy.ipynb) **for a Jupyter notebook tutorial on numpy**

```py
import numpy as np
```

* * *

### Arrays creation and properties

-   `numpy` arrays are statically typed and homogeneous. The type of the elements is determined when the array is created.
-   `np.array(list)` generate an array from a list
-   `np.shape(array)` , `np.size(array)` , `np.ndim(array)`print dimensions, number of elements and number of dimensions of the array
-   `np.dtype(list)` print the data type of the array

#### Array generation from functions

-   `np.arange(first,size,spacing)` generate an array
-   `np.linspace(first, last, size)` — both end points are included
-   `np.logspace(first, last, size, base=e)` — both end points are included
-   `np.zeros((dim1,dim2))` and `np.ones((dim1,dim2))` creates arrays of 0s and 1s
-   `np.random.rand(d0,d1,...)`  generate a `d0, d1,…` dimension array made of **uniformly distributed random numbers** between 0 and 1
-   `np.random.randn(d0,d1,...)`  generate a `d0, d1,…` dimension array made of **gaussian distributed random numbers** between 0 and 1

#### Array generation from files

-   `data = np.genfromtxt('csv-or-tsv-file.dat')` to import data from a CSV or TSV value

#### Save arrays in file

-   `savetxt('file-name.csv',array-name,fmt='%.5f')` save the array in a cvs file and specify the format (optional)
-   `np.save(‘file-name.npy’,array-name)` and `np.load(‘file-name.npy’)` save and load arrays in proprietary format

* * *

### Arrays manipulation

-   `array[index1, index2]` print the element in the corresponding place. If a dimension is omitted or substituted with `:`, print the whole line
-   `array[lower:upper:step]` array slicing
-   `np.nditer(array)` create an iterator object that could be used in `for` loops
-   `np.random.permutation(array)` -> shuffle the array (can also be a pandas Series)

* * *

### Linear Algebra

-   `np.zeros(a)` return _array of 0s_ with dimensions `a` [doc](https://docs.scipy.org/doc/numpy/reference/generated/numpy.zeros.html?highlight=zeros#numpy.zeros)
-   `ndarray.shape` return a tuple with the **array dimensions** [doc](https://docs.scipy.org/doc/numpy-1.15.0/reference/generated/numpy.ndarray.shape.html)
-   `np.dot(a,b)` **dot product** of 2 arrays/matrices [doc](https://docs.scipy.org/doc/numpy/reference/generated/numpy.dot.html#numpy.dot)

* * *

### Data Processing

-   `mean(array)` find the mean value of the data in the dataset
-   `std(array)` and `var(array)` standard deviation and variance
-   `array.min()` and `array.max()` min and max values
-   `sum(array)` and `cumsum(array)` sum and cumulative sum all the values in the array
-   `prod(array)` and `cumprod(array)` product and cumulative product of all the values of the array
