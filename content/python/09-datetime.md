---
title: Time and Datetime
draft: false
arguments:
  - Get Current Date
weight: 09
---

([Docs](https://docs.python.org/3/library/datetime.html))

```py
from datetime import datetime as dt
from datetime import date
import time
```

### Datetime

#### `datetime` Submodule

- `dt.datetime.now()` &rarr; return **current date and time** in standard format
    
    - `dt.datetime.now().strftime('%Y-%m-%d %H:%M:%S.%f')` &rarr; format the returned valued

    - `dt.datetime.now().time()` &rarr; return only the date

#### `date` Submodule

- `date.today()` &rarr; return **current date**

* * *

### `dateutil` module

This module expands the `datetime` module.

- To check if a string represent a date use

```py
    from dateutil.parser import parse

    try:
        parse(string, fuzzy=False)
    except ValueError:              # it is not a date
        pass
```

* * *

### Time

- `time.perf_counter()` &rarr; return value (in seconds) of a performance counter (calcualted from the highest clock). Used to measure performance. The single value is useless, it is required to make difference between consecutive results ([doc](https://docs.python.org/3/library/time.html#time.perf_counter))

* * *

### Resources

- [`dateutil` docs](https://dateutil.readthedocs.io/en/stable/)
