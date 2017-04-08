# Defining Machine Learning

Machine learning is learning models from data.  What you’re learning isn’t the data, but a model that will help you understand \(and possibly also explain\) it.  Examples include: 

* Which advert is the user most likely to click on?
* Who's most likely to win this election? 
* Which wells are most likely to fail in the next 6 month?

## Machine learning as predictive analytics

 ![](/assets/Screen Shot 2017-04-08 at 5.10.34 PM.png)Image: the data science escalator, from http://www.rosebt.com/blog/descriptive-diagnostic-predictive-prescriptive-analytics

We bother making models because we want to start asking questions, and \(hopefully\) making changes in our world.

## Machine Learning Process

Like data science, there's a procss associated with machine learning: 

* Get data
* Select a model
* Select hyperparameters for that model
* Fit model to data
* Validate model \(and change model, if necessary\)
* Use the model to predict values for new data

This is also known as import-instantiate-fit-predict.  'Hyperparameters' are things like “how many clusters of data do I think there are in this dataset?”

## The Scikit-Learning library

The scikit-learn Python library contains many classic and useful machine learning algorithms.  There are lots of great scikit-learn tutorials on [http://scikit-learn.org/stable/](http://scikit-learn.org/stable/)

NB the import name for scikit-learn is "sklearn", but you'll never see "import sklearn" in code; instead you'll see individual objects being imported from it, e.g. "from sklearn.neighbors import KNeighborsClassifier"

Scikit-learn comes with a set of example datasets: you’ll see these a lot when people discuss algorithms online.  The ones you're most likely to see are iris \(measurements for a set of flowers\), digits \(handwritten numbers\), diabetes \(people with diabetes\) and boston \(Boston housing market data\).







