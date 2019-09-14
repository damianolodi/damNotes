---
title: "Matplotlib"
draft: false
arguments: ["Superimposing Figures",
            "Multiple Axis",
            "Plot Annotations",
            "Plot Animation",
            "Custom Plot Styles"]
weight: 3
---

Jupyter Notebook [tutorial](http://nbviewer.jupyter.org/github/jrjohansson/scientific-python-lectures/blob/master/Lecture-4-Matplotlib.ipynb) on matplotlib.
[Official documentation](https://matplotlib.org/)

```py
import matplotlib.pyplot as plt
%matplotlib inline # display figures inside jupyter notebooks

axes.plot(a, b, 'b.-',
          color = '#FFFFFF',    # color (control)
          alpha = 0.5,
          lw = 3,               # linewidth
          ls = '-',             # linestyle '-' '--' '-.' ':' 'steps'
          marker ='+',          # markerstyle `+`, `o`, `*`, `s`, `,`, `.`, `1`, `2`, `3`,…
          ms = 3                # markersize
          )
```

### Basic figure script

#### Create a small figure on top of another one

```py
#request text elements rendering with Latex
matplotlib.rcParams.update({'font.size': 18, 'text.usetex': True})

# create the figure object
fig = plt.figure(figsize=(8,4), dpi=100) # figsize in inch
# create an axes object inside the figure
axes1 = fig.add_axes([0.1, 0.1, 0.8, 0.8]) # left, bottom, width, height
axes2 = fig.add_axes([0.2, 0.5, 0.4, 0.3])

# main figure
axes1.plot(x, y, 'r', label=r'curve1 \alpha')
axes1.plot(x, y, 'r', label=r'curve2')
axes1.set_xlabel(r'x')
axes1.set_xlim([min,max])
axes1.set_ylabel(r'y')
axes1.set_ylim([min,max]) # set only an extreme using `left` - `right` or `top` - `bottom`
axes1.set_title(r'title')
axes1.legend(loc=0)

# insert
axes2.plot(y, x, 'g')
axes2.set_xlabel(r'y')
axes2.set_ylabel(r'x')
axes2.set_title(r'insert title'); # use raw input in strings to avoid conflicts with LaTex
axes2.axis('log') # set axis scale

# save the figure
fig.savefig('file-name.png', dpi=200)
```

-   can plot pandas df with `ax.plot('column1', 'column2', 'r--', obj=df)`
-   `axes1.legend()` &rarr; more details [about location](https://matplotlib.org/users/legend_guide.html#legend-location)

#### Multiple axis on the same figure

```py
fig, axes = plt.subplots(nrows = 1, ncols = 2,
                         figsize = (8,4), dpi = 100,
                         sharex = True, sharey = False #share axis in subpplots
                         )
plt.subplots_adjust(wspace=0,hspace=0) # adjust space between subplots in a figure

fig.tight_layout() # apply at the end to correct overlapping content
```

-   [Plots gallery](https://matplotlib.org/gallery.html)

* * *

### Plot Annotation and Drawing

Annotate text and arrows

```py
# Annotate with text
ax.text(x, y,                   # coordinates
        'Hello world!',         # text
        family = 'monospace',
        fontsize = 10,
        rotation = 90           # text rotation
        )

# Draw line
ax.axvline(x = value,   # create vertical line in the plot
           color='r',
           linewidth=1)

# Draw arrow
ax.annotate(label,
			xy = (x, y),        # point position
            xytext = (x, y),    # text position
            arrowprops = dict(facecolor = 'black',
							  headwidth = 4,
							  width = 1,
                              headlength = 4),
            horizontalalignment = 'left',
			verticalalignment = 'top')
```

* * *

### Plot Animations

1.  `conda install -c conda-forge ffmpeg` &rarr; install `ffmpeg`

2.  `import matplotlib.animation as animation` &rarr; import the animation package

3.  `%matplotlib notebook` &rarr; allow dynamic plots in the Jupyter Notebook

4.  create figure as usual

5.  create a writer with the following code

```py
Writer = animation.writers['ffmpeg']
writer = Writer(fps = 20, # used when saving the movie in a file
                metadata = dict(artist = 'Damiano'),
                bitrate = 1800
                )
```

6.  create a function that will be used to animate the plot, like:

```py
    def animate(i):
        data = data_prova.iloc[:int(i+1)]
        plot_ax.plot(data['Tempo Trascorso [s]'], data['P_tot '], 'b-', lw=1, ms=3)
	        # plot a text on the figure and update it in each frame
            ## the probability_text variable needs to be initialized outside the function
            if data['P_tot '].iloc[int(i)]>=0.75:
                probability_text2.set_text('%.2f' % data['P_tot '].iloc[int(i)])
            else:
                probability_text.set_text('%.2f' % data['P_tot '].iloc[int(i)])
```

7.  create the animation object (? controlla)

    -   `animate` is the name of the animation function. it can have more variables, but the `i` is incremented automatically

    -   `interval` is the interval (in ms) between two frames in the animation

    -   `frames` is the number of frames that are generated in that way

```py
        ani = matplotlib.animation.FuncAnimation(plot_fig,
                                                 animate,
                                                 interval=int(frame_delay),
                                                 frames=len(data_prova['Tempo Trascorso [s]']),
                                                 repeat=False)
```

8.  `ani.save(save_path+'/name.mp4', writer=writer)` &rarr; save

* * *

### Custom Plot Style

_[Windows machine, Python installed using Miniconda 3 (for Anaconda it should be the same)]_

The idea is to create a **custom style file** in the same directory where all the styles are archived. The instruction reported on the documentation probably are correct only for a "normal" Python installation. This is the process to follow if Miniconda is installed:

1.  navigate into the matplotlib style folder (mine is in `C:\Users\UserName\Miniconda3\Lib\site-packages\matplotlib\mpl-data\stylelib`)

2.  create a file named `style-name.mplstyle` and write in it the styles as reported on the documentation

3.  in the code use the following

```python
import matplotlib.pyplot as plt
%matplotlib inline #if you are using jupyter
plt.style.use('style-name')
```
