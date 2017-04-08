# Select a model

The first part of machine learning is selecting the type of model that you want to use with your dataset.

Models can be roughly organized into supervised and unsupervised learning: 

● supervised = give the algorithm both input data and the answers for that data \(kinda like teaching\), and it learns the connection between data and answers; comes in two main flavors: 

* Regression: learning numbers
* Classification: learning classes

● unsupervised = give the algorithm just the data, and it finds the structure in that data; two main flavors are: 

* Clustering: finding groups
* Dimensionality reduction: finding efficient representations 

Other types of learning exist, but most of the algorithms you see will be one of the four types above \(e.g. regression, classification, clustering or dimensionality reduction\).  For completeness, these other types are: 

* Semi-supervised learning \(where you only have a few answers\) does exist, but isn’t talked about much.  
* There’s also reinforcement learning, where you know if a result is better or worse, but not how much it’s better or worse.

## Regression: predict values

![](/assets/Screen Shot 2017-04-08 at 5.31.22 PM.png)The simplest form of learning is linear regression:  

* Fit a line to a set of datapoints
* Use that line to predict new values.  

### First, get your data

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

The code above creates 40 random samples around the line y = 3x + 7.   Random.rand selects from a uniform distribution; random.randn selects from a standard normal distribution. 

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
![](/assets/Screen Shot 2017-04-08 at 5.35.23 PM.png)Linear regression is good if your data is nicely linear.  Reality can be a little more challenging.  This is a 1-feature linear regression on the Diabetes dataset.  This is where you need to change your model.  In this case, you’d start by trying more features, then adapting the model hyperparameters \(e.g. it might not be a straight line that you need to fit\) or the model that you use \(e.g. linear regression might not be the best model type to use on this dataset\). 

## Classification: Predict classes

A class is a feature that can be in one of a set of possible states. For instance, these are all classes, with the states that we've assigned to them: 

* Well pump: \[working, broken\]
* CV: \[accept, reject\]
* Gender: \[male, female, others\]
* Iris variety: \[iris setosa, iris virginica, iris versicolor\]

Classification is finding the link between data and classes. When there are just two classifications, it’s called binary classification.   
![](/assets/Screen Shot 2017-04-08 at 5.43.12 PM.png)

This is the Iris dataset. It’s one of Scikit-learn’s example datasets. 

  


  


