# Machine Learning with Text Data

If you’re processing text, machine learning algorithms can be surprisingly useful \(if you’ve ever tried tagging thousands of tweets, you’ve learnt this lesson the hard way\).  Here are some examples.

## Classifying Text

Words are a valid input to machine learning algorithms. In this example, we’re using:

* Newsgroup emails as samples \(‘rows’ in our input\)
* Words in each email as features \(‘columns’\)
* Newsgroup ids as targets

This example comes from the scikit-learn training pages. We’re going to walk through it slowly, and explain what’s happening in each step.

### The 20Newsgroups Dataset

`from sklearn.datasets import fetch_20newsgroups`

`cats = ['alt.atheism', 'soc.religion.christian',  'comp.graphics', 'sci.med']`

`twenty_train = fetch_20newsgroups( subset='train', categories=cats)`

`twenty_test = fetch_20newsgroups(subset='test', categories=cats)`

One of Scikit-learn’s example datasets is all the text from a set of early newsgroup posts.  We’re going to use that, but restrict the ones that read to just 4 subjects: atehism, christianity, computer graphics and medicine.  Here’s how to get that dataset.

## Example Email

  
![](/assets/Screen Shot 2017-04-11 at 6.47.01 AM.png)Here’s the first post \(email\) in the dataset.  It appears to be about computer graphics.

### Convert Words to TFIDF Scores

`from sklearn.feature_extraction.text import CountVectorizer`

`from sklearn.feature_extraction.text import TfidfTransformer`

`count_vect = CountVectorizer()`

`X_train_counts = count_vect.fit_transform(twenty_train.data)`

`tfidf_transformer = TfidfTransformer(use_idf=True)`

`X_train_tfidf = tfidf_transformer.fit_transform(X_train_counts)`

We first create a bag of words for every post in our dataset.

We don’t want words to be weighted as more important than they should be \(e.g. we want to pay attention to rare words in the dataset\), so we use Scikit-learn’s TfidfTransformer function to convert this to a set of tfidf scores.

### Fit your model to the data

`from sklearn.naive_bayes import MultinomialNB`

`nb_classifier = MultinomialNB().fit(X_train_tfidf, twenty_train.target)`

Then we use the newsgroup labels \(atheism etc\) as classes, to learn the association between sets of words in posts and these labels.  We’re using a naïve Bayes algorithm as a classifier because although it probably won’t give the most accurate results possible, it’s pretty hard to break.

### Test your model

`docs_test = ['God is love', 'OpenGL on the GPU is fast']`

`X_new_counts = count_vect.transform(docs_test)`

`X_new_tfidf = tfidf_transformer.transform(X_new_counts)`

`predicted = nb_classifier.predict(X_new_tfidf)`

`for doc, category in zip(docs_test, predicted):`

`     print('{} => {}'.format(doc, twenty_train.target_names[category]))`

And then we feed the classifier two pieces of text that it hasn’t seen before, to see which classes it puts them in.  Go on: try this with your own example text!

## Text Clustering

We can also ‘cluster’ documents

The ‘distance’ function is based on the words they have in common

Common machine learning algorithms for text clustering include:

* Latent Semantic Analysis
* Latent Dirichlet Allocation

Other machine learning algorithms can be used on text data: unsupervised clustering is often used to see which documents can be grouped together \(e.g. into topics\).

  


