---
title: "Pandas"
draft: false
arguments: ["Dataframes",
			"File I/O",
			"df Manipulation",
			"df Merging"]
weight: 2
---

```py
import pandas as pd

# df creations
pd.Series([list]) 						# create a Series object
pd.DataFrame(dict) 						# create df from dictionary
pd.DataFrame(data=[list], index=None,	# create df from list
			 columns=None, dtype=None,
			 copy=False)
```

-   `df` &rarr; DataFrame
-   `s` &rarr; Series
-   Jupyter Notebook [lessons](https://bitbucket.org/hrojas/learn-pandas) on pandas

* * *

### File I/O

```py
df = pd.read_csv(r’relative_path’, 					#can be a web address
				sep = ' ',
                usecols = [0, 1, 5] 				# columns to be returned from the file
				names = ['column1','column2',...],
				header = None, 						# line of the header
                nrows = 5, 							# number of rows to read
				skiprows = 1, 						# rows to skip from top
				skipfooter = 3, 					# rows to skip from bottom
                									## if a list is provided, it will skip those rows
				index_col = False, 					# force to not use a column as the index of the rows
				skipinitialspace = True,			# skip initial spaces after delimiter
				parse_dates = [0], 					# list of ints or column names containing date time format
				infer_datetime_format = True 		# infer time format and switch to faster loading (if possible)
                )
```

-   `pd.read_json(path)` &rarr; **import** .json into a df

-   `pd.read_excel(path)` &rarr; **import** .xlsx into a df

-   `pd.to_csv(path)`, `pd.to_json(path)` and `pd.to_excel(path)` &rarr; **export** to .csv, .json or .xlsx file

* * *

### `df` properties

-   `df.info()` &rarr; return informations about the dataframe

-   `df.shape()` &rarr; return number of rows and columns (tuple)

-   `df.head(n=5)`, `df.tail(n=5)` &rarr; prints the first or last _n_ values

-   `df.describe()` &rarr; return **statistics** on the column

-   `df.values` &rarr; return the values in the _df_ as an **ndarray**

-   `df.dtypes` &rarr; return **type** of each column

-   `df['columnName'] = df['columnName'].astype(type)` &rarr; **change the type** of the column [`str` (printed as object), `int64`, `float64`]

* * *

### `df` Manipulation

-   `df.index` &rarr; access the indexes

-   `df.reindex([list])` &rarr; reassign indexes manually

-   `df.rename(columns={oldName1: newName1, ...}, inplace = True)` &rarr; **rename** columns

-   `df = df.drop('columnName', axis=1)` &rarr; **delete** a column

    -   alternatively use `df.drop(columns='columnName', inplace=True)`

-   `df = df.drop(indexNumber,axis=0)` &rarr; **delete** rows

-   `df.insert(location, columnName, values)` &rarr; **insert** a new column in location

-   `df.copy(deep=True)` &rarr; copy the `df` indices and data ([doc](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.copy.html#pandas-dataframe-copy))

-   `df.sort_values(['columnName'], ascending=False)` &rarr; **sort** values of _df_

-   `df[‘columnName’].unique()` &rarr; print the **unique values** of the column

-   `name = df.groupby('columnName')` &rarr; create a **groupby object**. Then, apply methods to this objects [e.g. like `name.sum()`]

-   `df.dropna()` &rarr; **remove rows** with NaN

-   `df.fillna(new_value)` &rarr; **replace** missing values

-   `df.apply(lambda_function)` &rarr; apply a lambda function to the _df_

-   `df.iloc[0:n,:]` &rarr; select the first _n_ rows and all the columns

-   `df.loc[44,:]` &rarr; select line 44 [only usable if there is an _index_ in the dataframe]

-   `df[df["Area"] == "Ireland”]` &rarr; select rows where _Area_ is _Ireland_

-   `pd.to_datetime(data, )` &rarr; **convert to datetime** format [doc](https://pandas.pydata.org/pandas-docs/stable/generated/pandas.to_datetime.html)

-   `df['columnName'].rolling(int).mean()` &rarr; return a Series with the moving average of the data [`int` is the window size]

    -   `mean()` can be replaced by whichever needed method

* * *

### Data Analysis

-   `df['columnName'].sum()`

-   `df['columnName'].mean()`

-   `df['columnName'].count()`

-   `df['columnName'].median()`

-   `df.min()` and `df.max()`

-   `df.corr(method=Pearson)` &rarr; compute pairwise correlation of columns ([doc](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.corr.html#pandas-dataframe-corr)) - ([Pearson Correlation Coefficient - Wikipedia](https://en.wikipedia.org/wiki/Pearson_correlation_coefficient)).

* * *

### Merging and Joining dataframes

[docs](http://pandas.pydata.org/pandas-docs/stable/generated/pandas.DataFrame.merge.html), [tutorial](https://www.shanelynn.ie/merge-join-dataframes-python-pandas-index-1/)

```py
new_df = pd.merge(df_1,
                  df_2[['use_id', 'column2', 'column3']],
                  on='use_id', 							# set the common column to merge on
				  										## [no need to be called the same]
				  how = 'inner', 						# specify merge type
				  indicator=True 						# create new column that explain 
				  										## if the row was present in both df or just one
				  )
```

#### Merge types

-   **Inner merge** (default): _keeps only the common values_ in both the left and right dataframes for the result

-   **Left merge** or **Right merge**: _keep every row in the left or right dataframe_. If there are missing values in the `on` column of the left/right dataframe, add empty/NaN values in the result.

-   **Outer merge**: _returns all the rows from the left dataframe, all the rows from the right dataframe, and matches up rows where possible_, with NaNs elsewhere.

    -   **WARNING: merging on _float_ can be painful**. Merge on _int_ or _string_.
