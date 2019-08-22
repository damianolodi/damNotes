---
title: "Seaborn"
draft: false
---

([Docs](http://seaborn.pydata.org/index.html))

```py
import seaborn as sns

sns.set()
tips = sns.load_dataset("tips") # or just load a dataframe with pandas
sns.relplot(x = "total_bill",
            y = "tip",
            col = "time",
            hue = "smoker",
            style = "smoker",
            size = "size",
            data = tips);
```

-   `sns.set()` set the style of the plot using `matplotlib` standards ([doc](http://seaborn.pydata.org/tutorial/aesthetics.html#aesthetics-tutorial))
