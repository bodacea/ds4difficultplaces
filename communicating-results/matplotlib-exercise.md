# Matplotlib Exercises

Let’s create a simple visualisation in matplotlib \(the Python plotting library\). 

## Draw a line chart

`%matplotlib inline # notebook only)`

`import matplotlib.pyplot as plt`

`import numpy as np`

`x = np.linspace(0, 10, 100)`

`y = np.sin(x)`

`plt.plot(x, y)`

`plt.show() # not notebook`

![](/assets/Screen Shot 2017-03-26 at 7.09.49 PM.png)NB: You only need the %matplotlib inline in an ipython notebook.

## Draw a Scatterplot

`import matplotlib.pyplot as plt`

`import numpy as np`

`x = np.array([1,4,3,2,6,4,7,8])`

`y = np.array([3,5,4,3,7,6,4,9])`

`plt.scatter(x, y)`

![](/assets/Screen Shot 2017-03-26 at 7.12.34 PM.png)

## Add Labels to your Plot

`fig, ax = plt.subplots()`

`plt.scatter(x, y)`

`ax.set_ylabel('This is the Y axis')`

`ax.set_xlabel('This is the X axis')`

`ax.set_title('This is the Title')`

`plt.show() # not notebook`

![](/assets/Screen Shot 2017-03-26 at 7.13.45 PM.png)  
plt.subplots creates a plot on your drawing ‘canvas’. It’s what we usually use to create a group of plots. Here, we’re using it to get at the axes \(ax\) for this visualisation.

