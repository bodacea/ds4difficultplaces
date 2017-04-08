# Select a model

The first part of machine learning is selecting the type of model that you want to use with your dataset.

Models can be roughly organized into supervised and unsupervised learning:

● supervised = give the algorithm both input data and the answers for that data \(kinda like teaching\), and it learns the connection between data and answers; comes in two main flavors:

* Regression: learning numbers
* Classification: learning classes

● unsupervised = give the algorithm just the data, and it finds the structure in that data; two main flavors are:

* Clustering: finding groups
* Dimensionality reduction: finding efficient representations 

Other types of learning exist, but most of the algorithms you see will be one of the four types above \(e.g. regression, classification, clustering or dimensionality reduction\).  For completeness, these other types are:

* Semi-supervised learning \(where you only have a few answers\) does exist, but isn’t talked about much.  
* There’s also reinforcement learning, where you know if a result is better or worse, but not how much it’s better or worse.

## Regression: predict values

![](/assets/Screen Shot 2017-04-08 at 5.31.22 PM.png)The simplest form of learning is linear regression:

* Fit a line to a set of datapoints
* Use that line to predict new values.  

### Get your data

`import numpy as np`

`import pandas as pd`

`%matplotlib inline`

`import matplotlib.pyplot as plt`

`gen = np.random.RandomState(42)`

`num_samples = 40`

`x = 10 * gen.rand(num_samples)`

`y = 3 * x + 7+ gen.randn(num_samples)`

`X = pd.DataFrame(x)`

`plt.scatter(x,y)`

The code above creates 40 random samples around the line y = 3x + 7.   Random.rand selects from a uniform distribution; random.randn selects from a standard normal distribution.

### Fit model to data

`from sklearn.linear_model import LinearRegression`

`model = LinearRegression(fit_intercept=True)`

`model.fit(X, y)`

`print('Slope: {}, Intercept: {}'.format(model.coef_, model.intercept_))`

Note the hyperparameter \(fit\_intercept\). This says that your model doesn’t start at \(0,0\).

### Check your model

`Xtest = pd.DataFrame(np.linspace(-1, 11))`

`predicted = model.predict(Xtest)`

`plt.scatter(x, y)`

`plt.plot(Xtest, predicted)`

`plt.show()`

`print('predicted slope is {}, predicted intercept is'.format(model.coef_, model.intercept_))`  
![](/assets/Screen Shot 2017-04-08 at 5.35.23 PM.png)Linear regression is good if your data is nicely linear.  Reality can be a little more challenging.  This is a 1-feature linear regression on the Diabetes dataset.  This is where you need to change your model.  In this case, you’d start by trying more features, then adapting the model hyperparameters \(e.g. it might not be a straight line that you need to fit\) or the model that you use \(e.g. linear regression might not be the best model type to use on this dataset\).

## Classification: Predict classes

A class is a feature that can be in one of a set of possible states. For instance, these are all classes, with the states that we've assigned to them:

* Well pump: \[working, broken\]
* CV: \[accept, reject\]
* Gender: \[male, female, others\]
* Iris variety: \[iris setosa, iris virginica, iris versicolor\]

Classification is finding the link between data and classes. When there are just two classifications, it’s called binary classification.  
![](/assets/Screen Shot 2017-04-08 at 5.43.12 PM.png)

This is the Iris dataset. It’s one of Scikit-learn’s example datasets. A sepal is one of the leaves that wrap around a flower's petals. 

### Get Your Data

`import numpy as np`

`from sklearn import datasets`

`iris = datasets.load_iris()`

`X = iris.data`

`Y = iris.target`

`print("Targets: {}".format(iris['target_names']))`

`print("Target data: {}".format(iris_Y))`

`print("Features: {}".format(iris['feature_names']))`

`print("Feature data: {}".format(iris_X))`

### Split your data

`ntest=10`

`np.random.seed(0)`

`indices = np.random.permutation(len(X))`

`iris_X_train = X[indices[:-ntest]]`

`iris_Y_train = Y[indices[:-ntest]]`

`iris_X_test = X[indices[-ntest:]]`

`iris_Y_test = Y[indices[-ntest:]]`

`print(‘{} training points, {} test points’.format(len(iris_X_train), len(iris_X_test)))`

Why do we split into training and test sets?  This is called a “holdout” set… we save some of our data, so we can use it to check how well our classifier does on data it hasn’t seen before.

### Fit model to data

`from sklearn.neighbors import KNeighborsClassifier`

`knn = KNeighborsClassifier(n_neighbors=5, metric='minkowski')`

`knn.fit(iris_X_train, iris_Y_train)`

This is the k nearest neighbours algorithm.  For every new datapoint, it looks at the N nearest datapoints it has classifications for, and assigns the new datapoint the class that’s most common amongst them. 

Here, we’re using 5 neighbours.  We’re also using the [Minkowski distance](https://machinelearning1.wordpress.com/2013/03/25/three-famous-metrics-manhattan-euclidean-minkowski/): this tells the algorithm how to compute the distance between two points, so we can define which points are ‘closest’.  Common distance metrics you’ll see in machine learning include:

* Manhattan, or “city block” distance: add the distance along the x axis to the distance along the y axis \(“city block” because that’s how you navigate in Manhattan”\)
* Euclidian distance: calculate the straight-line distance between the two points \(e.g. sqrt\(x^2 + y^2\)
* Minkowski distance: a variant of Euclidian distance, for large numbers of features

### Check your model

`predicted_classes = knn.predict(iris_X_test)`

`print('kNN predicted classes: {}'.format(predicted_classes))`

`print('Real classes:          {}'.format(iris_Y_test))`

##  Clustering: Find Groups in your Data

![](/assets/Screen Shot 2017-04-08 at 5.56.03 PM.png)

### Get your data

`from sklearn import datasets`

`iris = datasets.load_iris()`

`X = iris.data`

`Y = iris.target`

`print("Xs: {}".format(X))`

### Fit model to data

`from sklearn import cluster`

`k_means = cluster.KMeans(3)`

`k_means.fit(iris.data)`

### Check your model

`print("Generated labels: \n{}".format(k_means.labels_))`

`print("Real labels: \n{}".format(Y))`

## Dimensionality Reduction

![](/assets/Screen Shot 2017-04-08 at 5.59.32 PM.png)This is the digits example dataset, and the result of running a dimensionality reduction algorithm on it. 

## Recap: Choosing an Algorithm

Have: data and expected outputs

* Want numbers? Try regression algorithms
* Want classes?  Try classification algorithms

Have: just data

* Want to find structure? Try clustering algorithms
* Want to look at it? Try dimensionality reduction

There’s no “best” algorithm for every problem. This is also known as the “no free lunch” theory. If you have data and estimate of better/worse: reinforcement learning.  There are lots of variants on these algorithms: the [Scikit-learn cheat sheet](http://scikit-learn.org/stable/tutorial/machine_learning_map/) will help you choose between them.  



