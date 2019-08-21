---
title: "Pandas"
draft: false
---

* * *

-   `df.to_csv('path/fileName.txt',index=False,header=False, encoding='utf8')` **export dataframe to a text file**. Setting these parameters to False will prevent the index and header names from being exported.
    -   `df.to_excel(“output_excel_file.xlsx", sheet_name="Sheet 1", index=False)` use to export to Excel. This may need the `xlsxwriter` package.
-   `df.dtypes` print the **type of each column** of the dataframe
-   `df['columnName'] = df['columnName'].astype(type)` **change the type** of the column to `type`. Possible values:
    -   `str` string (printed as object)
    -   `int64`
    -   `float64`

### Dataframe creation

-   `pd.DataFrame(data=[list], index=None, columns=None, dtype=None, copy=False)`
-   `pd.Series([list])` create a Series object

* * *

### Data Analysis

-   `df.sort_values(['columnName'], ascending=False)` **sort** values of `df`
-   `df[‘columnName’].unique()` print the **unique values** of the column inserted
-   `name = df.groupby('columnName')` create a groupby object. We can then apply methods to this objects, like `name.sum()`
-   `df.[‘columnName’].describe()` ::**return basic statistics value**:: for the selected column, depending if numeric or string type.

* * *

### Operations on columns

-   `df.columnName` or `df['columnName']` or `df.iloc[:,<columnNumber>]` provide data selection. This returns a `pandas.Series` datatype, a 1D set of data.
-   `df['columnName'].sum()`
-   `df['columnName'].mean()`
-   `df['columnName'].count()`
-   `df['columnName'].median()`
-   `df.fillna(new_value)` replace missing values
-   `df.min()` and `df.max()`
-   `df= df.drop('columnName',axis=1)` **delete** a column
    -   alternatively use `df.drop(columns='columnName', inplace=True)`
-   `df.insert(location,columnName,values)` insert a new column in location (insert an `int`)
-   **Rename Columns**

```py
df.rename(columns={	‘pop’:’population’,
						’lifeExp’:’life_exp’,
						‘gdpPercap’:’gdp_per_cap’},
			 inplace=True)
```

-   `df.apply(lambda_function)` -> apply a lambda function to the DataFrame

* * *

### Operations on rows

-   `df.iloc[0:10,:]` select the first 10 rows and all the columns
-   `df.loc[44,:]` select the line 44. Only usable if there is an index in the dataframe
-   `df[df["Area"] == "Ireland”]` select rows where Area is Ireland
-   `df = df.drop(indexNumber,axis=0)` **delete** rows
-   `df.index` access the indexes
-   `df.reindex([list])` -> reassign indexes of the DataFrame manually
-   `df.dropna()` -> remove rows with NaN

* * *

### Plotting in pandas

Need the `matplotlib.pyplot` to make pretty figures and the `%matplotlib inline` in the Jupyter notebook to plot inline.
[Documentation](https://pandas.pydata.org/pandas-docs/stable/visualization.html) on plotting and data visualisation.
Use [Seaborn](bear://x-callback-url/open-note?id=B3615AA5-90D0-4F7B-A551-07F0BD80BA19-1982-000011D7C3A66189)  for exploiting data in pandas.

-   `df.hist('columnName)` -> generate a quick histogram on the selected column

* * *

### Merging and Joining dataframes

Merge [docs](http://pandas.pydata.org/pandas-docs/stable/generated/pandas.DataFrame.merge.html), [tutorial](https://www.shanelynn.ie/merge-join-dataframes-python-pandas-index-1/)

```py
new_df = pd.merge( df_1,
                   df_2[['use_id', 'column2', 'column3']],
                   on='use_id',
					  indicator=True)
```

-   the `on='common_column'` set the common column we want to merge on. They don’t need to be called the same
-   the `how='inner'` parameter specify the merge type
-   `indicator=True` apply a new column that explain if the row was present in both dataframe or just one of them
    ### Merge types
-   **Inner merge** (default): keeps only the common values in both the left and right dataframes for the result
-   **Left merge** or **Right merge**: keep every row in the left or right dataframe. Where there are missing values of the `on` variable in the right dataframe, add empty / NaN values in the result.
-   **Outer merge**: returns all the rows from the left dataframe, all the rows from the right dataframe, and matches up rows where possible, with NaNs elsewhere.
    ::**WARNING:** merging on _float_ can be painful. Merge on _int_ or _string_::

* * *

### Other Functions

-   `pd.to_datetime(data, )` convert to datetime format [doc](https://pandas.pydata.org/pandas-docs/stable/generated/pandas.to_datetime.html)
-   `df['columnName'].rolling(int).mean()` return a Series with the moving average of the data, where `int` is the window size.
    -   `mean()` can be replaced by whichever method you need
