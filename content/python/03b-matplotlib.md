---
title: "Matplotlib 2"
draft: false
---

**See** [here](http://nbviewer.jupyter.org/github/jrjohansson/scientific-python-lectures/blob/master/Lecture-4-Matplotlib.ipynb) **for a Jupyter notebook tutorial on matplotlib**
[Official documentation](https://matplotlib.org/)

```py
import matplotlib.pyplot as plt
```

Use `%matplotlib inline` in Jupyter to display figures inside the notebooks

### Basic figure script

This script create a small figure on top of another one

```py
#request text elements rendering with Latex
matplotlib.rcParams.update({'font.size': 18, 'text.usetex': True})

# create the figure object
fig = plt.figure(figsize=(8,4), dpi=100)
# create an axes object inside the figure
	# left, bottom, width, height (range 0 to 1)
axes1 = fig.add_axes([0.1, 0.1, 0.8, 0.8])
	# inset axes
axes2 = fig.add_axes([0.2, 0.5, 0.4, 0.3])

# main figure
axes1.plot(x, y, 'r',label=r'curve1 \alpha')
axes1.plot(x, y, 'r',label=r'curve2')
axes1.set_xlabel(r'x')
axes1.set_xlim([min,max])
axes1.set_ylabel(r'y')
axes1.set_ylim([min,max])
axes1.set_title(r'title')
axes1.legend(loc=0)

# insert
axes2.plot(y, x, 'g')
axes2.set_xlabel(r'y')
axes2.set_ylabel(r'x')
axes2.set_title(r'insert title');
axes2.axis('log')

# save the figure
fig.savefig('file-name.png', dpi=200)
```

### Specs

-   use raw input in strings to avoid conflicts with LaTex
-   can also print `pandas` dataframes with `ax.plot('column1','column2','r--',obj=df)`
-   `figsize` is a tuple of the width and height of the figure, in inch
-   `dpi` resolution
-   `axes1.legend()` add the legend for that axes. `loc` specify where to place the legend (more details [here](https://matplotlib.org/users/legend_guide.html#legend-location))
-   `axes1.set_xlim([min,max])` set axis limits
    		\* set only an extreme using `left` - `right` or `top` - `bottom`
-   `axes2.axis('log')` set logarithmic scale

#### Arguments

-   `color=#FFFFFF, alpha= 0.5` use in `plot()` to request special colours
-   `lw=3` change the line width
-   `ls='-'` change the line style ( use `-`, `--`, `-.`, `:`, `steps`)
-   `marker='+'` change the marker (use `+`, `o`, `*`, `s`, `,`, `.`, `1`, `2`, `3`,…)
-   `markersize=3` change the marker size
-   `linewidth=0.7` change line width

* * *

### Other functions

-   `fig, axes = plt.subplots(nrows=1, ncols=2,figsize=(8,4), dpi=100)` use instead of `plt.figure` to create multiple axes in a single figure.
    		_ `sharex=True` and `sharey` use to share axis in subplots
    			_ `plt.subplots_adjust(wspace=0,hspace=0)` adjust space between subplots in a figure
    		\* Apply `fig.tight_layout()` at the end so there is no overlapping content.
-   [Plots gallery](https://matplotlib.org/gallery.html)

* * *

### Annotating and Drawing on Plots

-   `ax.text(x, y, 'Hello world!', family='monospace', fontsize=10)` write text on the axis
    		_ `x` and `y` are the coordinates
    		_ `rotation=90` rotates text
-   `ax.axvline(x=value, color='r', linewidth=1)` create a vertical line in the plot

```py
ax.annotate( label,
				xy=(x, y), #posizione della punta
             xytext=(x, y), #posizione del testo
             arrowprops=dict(facecolor='black',
								 headwidth=4,
								 width=1,
                             headlength=4),
             horizontalalignment='left',
				verticalalignment='top')
```

Can annotate text and arrow

* * *

### Plot Animations

1.  Install `ffmpeg` on the system using `condo install -c conda-forge ffmpeg`
2.  Import the animation package with `import matplotlib.animation as animation`
3.  Declare `%matplotlib notebook` in the jupyter notebook to allow dynamic plots in it
4.  Create figure as usual
5.  Create a writer with the following code

```py
Writer = animation.writers['ffmpeg']
writer = Writer(fps=20, metadata=dict(artist='Damiano'), bitrate=1800)
```

    * `fps` is the number of frames per second that will be used when saving the movie in a file

6.  Create a function that will be used to animate the plot, like:

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

7.  Create the animation object (? controlla) using

```py
ani = matplotlib.animation.FuncAnimation(plot_fig, animate, interval=int(frame_delay) ,frames=len(data_prova['Tempo Trascorso [s]']), repeat=False)
```

    * `animate` is the name of the animation function. it can have more variables, but the `i` is incremented automatically
    * `interval` is the interval (in ms) between two frames in the animation
    * `frames` is the number of frames that are generated in that way

8.  Save using

```py
ani.save(save_path+'/name.mp4', writer=writer)
```
