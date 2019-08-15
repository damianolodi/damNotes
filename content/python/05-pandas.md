---
title: "Pandas"
draft: false
---

-   {`df` → DataFrame; `s` → Series}

-   `import pandas as pd`

* * *

### File I/O

-   `pd.read_csv(path); pd.read_json(path); pd.read_excel(path);` → **read** .csv, .json or .xlsx file.

-   `pd.DataFrame(dict)` → create a `df` from a dictionary.

-   `pd.to_csv(path); pd.to_json(path); pd.to_excel(path);` → **export** to .csv, .json or .xlsx file.

* * *

### `df` manipulation

-   `df.copy(deep=True)` → copy the `df` indices and data ([doc](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.copy.html#pandas-dataframe-copy)).

* * *

### Statistics

-   `df.corr(method=Pearson)` → compute pairwise correlation of columns ([doc](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.corr.html#pandas-dataframe-corr)) - ([Pearson Correlation Coefficient - Wikipedia](https://en.wikipedia.org/wiki/Pearson_correlation_coefficient)).
