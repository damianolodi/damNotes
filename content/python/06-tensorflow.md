---
title: "Tensorflow"
draft: false
---

-   `import tensorflow as tf`

-   `from tensorflow.python.data import Dataset` → select the `data` module in the Python API of Tensorflow and import a class

* * *

### `tf.data` module

-   [Docs](https://www.tensorflow.org/api_docs/python/tf/data)
-   `Dataset` class ([doc](https://www.tensorflow.org/api_docs/python/tf/data/Dataset))

* * *

### `tf.feature_column` module

-   `tf.feature_column.numeric_column` → create a numeric column for the model ([doc](https://www.tensorflow.org/api_docs/python/tf/feature_column/numeric_column)).

-   `tf.feature_column.bucketized_column(source_column, boundaries)` → takes a numeric column as input and apply binning using boundaries ([doc](https://www.tensorflow.org/api_docs/python/tf/feature_column/bucketized_column)).

-   `tf.feature_column.cross_column()` → returns a column to perform crosses of categorical features ([doc](https://www.tensorflow.org/api_docs/python/tf/feature_column/crossed_column))

* * *

### `tf.train` module

-   It offers support functions for training models ([doc](https://www.tensorflow.org/api_docs/python/tf/train))

-   `FtrlOptimizer` class used to implement the FTRL algorithm during training ([doc](https://www.tensorflow.org/api_docs/python/tf/train/FtrlOptimizer))
