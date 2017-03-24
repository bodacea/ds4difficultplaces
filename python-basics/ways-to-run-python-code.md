# Ways to run Python code

So you have some Python code - maybe written in these slides, maybe in a .py or .ipynb file. Let’s look at some of the ways you can run that code.

## Python in the terminal window

Type any of these inter the terminal window:

python

ipython

python helloworld.py

* ‘python’ runs the python interpreter. ‘ipython’ runs a version of the python interpeter that’s slightly friendlier to new users, e.g. it has better help.
* ‘python helloworld.py’ runs the python interpreter on a file called ‘helloworld.py’. If that file contains a set of python commands \(e.g. “print\(“Hello World!”\)”\), you’ll see the output of those commands. You can do the same thing with ipython, e.g. ‘ipython helloworld.py’. 

There’s a file called helloworld.py in your course notes. Try running it, then editing it \(any text editor will do, although some, like Sublimetext, are set up to point out any coding errors to you\), and running it again.

There are other ways to run Python code \(e.g. from another program\), but we won’t be doing that in this course.

## Jupyter Notebooks

Jupyter notebooks are files that contain both formatted text and code, that you view and run using a browser \(Chrome, Firefox, Safari etc\).  Depending on how you set up your notebooks, they can run code written in Python, R or several other languages.

Jupyter notebooks were originally called ipython notebooks: they’ll be called this in many places online. Apart from the name change, they’re fundamentally the same thing: text and code, mixed together. Wherever you see ‘ipython notebook’, use ‘jupyter notebook’; it'll work fine.

All the code examples \(Python and R\) for this course are in iPython notebooks, so you’ll need to know how to open one.

In the terminal window:

* ‘cd’ to the directory containing a .ipynb file
* Type “jupyter notebook”

NB cd \(“change directory”\) is the terminal window command to change directory. 

* “cd ~” takes you to your ‘top’ directory, where typing “ls” \(mac\) or “dir” \(windows\) will show you directories like Desktop, Downloads or Documents. 
* “cd dir1/dir2/dir3” takes you ‘down’ directories, to dir3 which is below dir2 which is below dir1.
   This is the terminal equivalent of starting in one directory, then clicking on dir1, dir2 then dir3.
* “cd ..” takes you ‘up’ directories: for instance, “cd ..” in dir3 will take you to dir2.
* “pwd” \(mac\) or “dir” \(windows\) will show you which directory you are in at the moment.
   If you get lost, type “cd ~”.

### Jupyter Dashboard

![](/assets/Screen Shot 2017-03-24 at 8.37.28 AM.png)  


Jupyter starts with the Dashboard view. This lists all the files in the directory that you called Jupyter from, including directories.  If you accidentally delete this view, open a web browser and type “localhost:8888” in the address window to get back to it. 

Things you need to know about in here:

* The “New” button on the top right hand side.
   Click on this, then “Python 3”, to create a new iPython notebook file.
* The file listing. Click on any file or directory to open it.
* The current directory \(the grey bar above the files list\): click on this to go back up from a directory.

### Jupyter Notebook

![](/assets/Screen Shot 2017-03-24 at 8.40.00 AM.png)

This is what you see when you open an iPython file.

The grey boxes are called ‘cells’. 

* You create a new cell by clicking ‘Insert’ on the top menu.
* You change the cell type \(to ‘Markdown’, or ‘Code’\) by clicking the box that currently says ‘Code’
* You run a cell by clicking in the cell, then clicking ‘cell’ -&gt;‘run cells’.
* You change your file’s name by clicking the name to the right of jupyter
* You save your shiny new file by clicking ‘File’ -&gt; ‘Save and Checkpoint’.

### Jupyter Notebook: Print View

![](/assets/Screen Shot 2017-03-24 at 8.42.56 AM.png)  
Don’t panic if your notebook looks like this when you open it. iPython has helpfully converted your markup cells into the way you’d see them if you printed the notebook. To edit any of these cells, click in the cell \(you should then see the markdown code, ready to edit\).

