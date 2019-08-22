---
title: "Other Libraries"
draft: false
---

### Datetime

-   `datetime.today()` → print **current date**

* * *

### IPython

#### `.display` module

([doc](https://ipython.readthedocs.io/en/stable/api/generated/IPython.display.html#module-IPython.display))

```py
from IPython import display # display various type of data (audio, images, ...)
```

-   `display.display(obj)` → display a python object in all frontends ([doc](https://ipython.readthedocs.io/en/stable/api/generated/IPython.display.html#module-IPython.display))

* * *

### PySerial

([Docs](https://pyserial.readthedocs.io/en/latest/shortintro.html))

```py
import serial

ser = serial.Serial(port = '/dev/tty.SLAB_USBtoUART',
                    baudrate = 9600,
                    bytesize = serial.EIGHTBITS,
                    parity = serial.PARITY_NONE,
                    stopbits = serial.STOPBITS_ONE,
					timeout = 3 #s
                    )
```

-   `python -m serial.tools.list_ports` → prints a list of available ports.

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
