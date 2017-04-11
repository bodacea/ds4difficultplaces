# Model Validation

## How well does the model fit new data?

“Holdout sets”:

* split your data into training and test sets
* learn your model with the training set
* get a validation score for your test set

## Overfitting and Underfitting

Models are rarely perfect… you might have to change parameters or model

* underfitting: model not complex enough to fit the training data
* overfitting: model too complex: fits the training data well, does badly on test

Overfitting: matches the training data well, performs badly on new data… has high variance

Underfitting: doesn’t match the training data well, might perform well on new data… has high bias

Bias/ Variance tradeoff: adjust your hyperparameters until the model performs well on the test data.

See e.g. [http://scott.fortmann-roe.com/docs/BiasVariance.html](http://scott.fortmann-roe.com/docs/BiasVariance.html)

This is all about your parameters  e.g. the difference between fitting a straight line, a quadratic curve or a n-dimensional curve. We’ll talk about the bias-variance tradeoff later. 

## Confusion Matrix

* True positive
* False positive
* False negative
* True negative

False positive is also known as a “type 1 error”; false negative is also known as a “type 2 error”. 

## Metrics

* Precision: of all the “true” results, how many were actually “true”?
  * Precision = tp / \(tp + fp\)
* Recall: how many of the things that were really “true” were marked as “true” by the classifier?
  * Recall = tp / \(tp + fn\)
* F1 score: harmonic mean of precision and recall
  * F1\_score = 2 \* precision \* recall / \(precision + recall\)
* Support: how many things that are actually this class did we use to calculate these metrics?

These numbers are always between 0 and 1. If you want to play with F1, try it in Python, e.g.:

`import numpy as np`

`p = np.array([.25, .25, .125, .5, .75])`

`r = np.array([.001, .10, .7, .9, .3])`

`2*p*r / (p + r)`

### Iris Classification Metrics

`from sklearn import metrics`

`print(metrics.classification_report(iris_Y_test, predicted_classes))`

  


