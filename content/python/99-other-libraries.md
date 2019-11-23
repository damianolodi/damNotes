---
title: Other Libraries
draft: false
arguments:
  - IPython
  - ScyPy
  - SymPy
  - Sys
weight: 99
---

### IPython

#### `.display` module

([doc](https://ipython.readthedocs.io/en/stable/api/generated/IPython.display.html#module-IPython.display))

```py
from IPython import display # display various type of data (audio, images, ...)
```

-   `display.display(obj)` &rarr; display a python object in all frontends ([doc](https://ipython.readthedocs.io/en/stable/api/generated/IPython.display.html#module-IPython.display))

* * *

### ScyPy

The SciPy framework builds on top of the low-level NumPy framework for multidimensional arrays, and provides a large number of higher-level scientific algorithms.
**See** [here](http://nbviewer.jupyter.org/github/jrjohansson/scientific-python-lectures/blob/master/Lecture-3-Scipy.ipynb) **for a Jupyter notebook tutorial on scypy**

```py
import scipy as sp
```

* * *

### SymPy

It is a Computer Algebra System (CAS). [Documentation](https://www.sympy.org/en/index.html)
**Sage** [docs](http://www.sagemath.org/) is in some aspects more powerful than SymPy, but both offer very comprehensive CAS functionality. The advantage of SymPy is that it is a regular Python module and integrates well with the IPython notebook.

**See** [here](http://nbviewer.jupyter.org/github/jrjohansson/scientific-python-lectures/blob/master/Lecture-5-Sympy.ipynb) **for a Jupyter notebook tutorial on symp**

```py
import sympy as symp
```

* * *

### Sys

- `sys.version` &rarr; contains python version installed on the machine

- `sys.executable` &rarr; contains information about the interpreter used

- `sys.platform` &rarr; contains information about the OS that is executing the code ([doc](https://docs.python.org/3.8/library/sys.html#sys.platform))
