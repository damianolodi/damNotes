---
title: "Datetime"
draft: false
arguments: ["Get Current Date"]
weight: 09
---

([Docs](https://docs.python.org/3/library/datetime.html))

```py
import datetime as dt
```

- `dt.datetime.now()` &rarr; return **current date and time** in standard format
    
    - `dt.datetime.now().strftime('%Y-%m-%d %H:%M:%S.%f')` &rarr; format the returned valued

    - `dt.datetime.now().time()` &rarr; return only the date

-   `datetime.today()` &rarr; return **current date**
