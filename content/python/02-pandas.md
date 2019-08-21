---
title: "Pandas"
draft: false
arguments: [""]
---

```py
import pandas as pd

# df creations
pd.DataFrame(dict) # create df from dictionary
```

-   `df` → DataFrame
-   `s` → Series
-   Jupyter Notebook [lessons](https://bitbucket.org/hrojas/learn-pandas) on pandas

* * *

### File I/O

Import file into a df

```py
df = pd.read_csv(r’relative_path’, #can be a web address
				sep = ' ',
                usecols = [0, 1, 5] # columns to be returned from the file
				names = ['column1','column2',...],
				header = None, # line of the header
                nrows = 5, # number of rows to read
				skiprows = 1, # rows to skip from top
				skipfooter = 3, # rows to skip from bottom
                ## if a list is provided, it will skip those rows
				index_col = False, # force to not use a column as the index of the rows
				skipinitialspace = True, # skip initial spaces after delimiter
				parse_dates = [0], # list of ints or column names containing date time format
				infer_datetime_format = True # infer time format and switch to faster loading (if possible)
                )
```

-   `pd.read_json(path)` → **import** .json into a df

-   `pd.read_excel(path)` → **import** .xlsx into a df

-   `pd.to_csv(path)`, `pd.to_json(path)` and `pd.to_excel(path)` → **export** to .csv, .json or .xlsx file

* * *

### `df` properties

-   `df.info()` → return informations about the dataframe

-   `df.shape()` → return number of rows and columns (tuple)

-   `df.head(n=5)`, `df.tail(n=5)` → prints the first or last _n_ values

-   `df.describe()` → return **statistics** on the column

-   `df.values` → return the values in the _df_ as an **ndarray**

* * *

### `df` manipulation

-   `df.copy(deep=True)` → copy the `df` indices and data ([doc](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.copy.html#pandas-dataframe-copy)).

* * *

### Statistics

-   `df.corr(method=Pearson)` → compute pairwise correlation of columns ([doc](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.corr.html#pandas-dataframe-corr)) - ([Pearson Correlation Coefficient - Wikipedia](https://en.wikipedia.org/wiki/Pearson_correlation_coefficient)).
