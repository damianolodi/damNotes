---
title: "Matplotlib"
draft: false
---

### Custom Plot Style

This process is considered for a Windows machine where Python is installed using Miniconda 3 (for Anaconda it should be the same).

The idea is to create a custom style file in the same directory where all the styles are archived. The instruction reported on the documentation probably are correct only for a "normal" Python installation. This is the process to follow if Miniconda is installed:

1.  navigate into the matplotlib style folder (mine is in `C:\Users\UserName\Miniconda3\Lib\site-packages\matplotlib\mpl-data\stylelib`)

2.  create a file named `style-name.mplstyle` and wrtite in it the styles as reported on the documentation

3.  in the code use the following

```python
import matplotlib.pyplot as plt
%matplotlib inline #if you are using jupyter
plt.style.use('style-name')
```
