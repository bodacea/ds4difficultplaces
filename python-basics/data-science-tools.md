# Data Science Tools

There are many data science tools out there: There are no hard and fast rules about which tool you should use for data science, beyond use the tools that do the job you need them to do, you’re comfortable with and that work for you.  Common tools include the Python, R and SQL programming languages, and tools for cleaning, processing and visualising data including OpenRefile, QGIS, D3, GDAL, Gephi, and Weka.

in these sessions, we’ll be concentrating on ones that are free, \(preferably\) open source, and available offline, with almost all programming done in Python. 

Python is a programming language.  You write a set of instructions to the computer \(e.g. "1+6"\), and the Python "interpreter" runs those instructions.  We'll go through the basics of Python in this section, with enough to understand the code used later on.  There are many better resources for learning Python in depth: see for instance [http://learnpythonthehardway.org/book/](http://learnpythonthehardway.org/book/) and [https://www.python.org/](https://www.python.org/).

We’ll cover the basics of Python in this session. The aim is to a\) get you some useful tools, and b\) not have you scared by something that looks like this.

```
from sklearn.neighbors import KNeighborsClassifier
knn = KNeighborsClassifier(n_neighbors=5,metric='minkowski')
knn.fit(iris_X_train,iris_Y_train)
```

The toolset for this course \(Python, R, offline tools\) was chosen so you can still do something useful when you have no internet / have low bandwidth. There are many other tools out there if you have the bandwidth to run then, but at some point in your career you’ll find yourself somewhere like Arusha in Tanzania, desperately hoping that the page you need will load. We’ve based this toolkit on trying to minimise that experience. Plus it’s cool being able to do things for yourself.





