# Reading Text Data

First we need to read in text-based data, and process it ready for algorithms and visualisations. 

Text data sources include: 

* Messages \(tweets, emails, sms messages...\)
* Document text \(reports, blogposts, website text…\)
* Audio \(via speech-to-text processing\)
* Images \(via OCR\)

## Reading Text Files

We’re looking at two pieces of data today: the Wikipedia entry for SIPA, and a set of tweets about the \#migrantcrisis, grabbed from the Twitter API. 

`fsipa = open('sipatext.txt', 'r')`

`sipatext = fsipa.read()`

`fsipa.close()`

`print(sipatext)`

Here’s the code to read in a raw text file. 

* If you want to work on pdf data, you’ll have to scrape it first \(see the earlier session on this\);
* For Microsoft Word documents, try the python-docx library.
* For speech recognition in python, try [https://pypi.python.org/pypi/SpeechRecognition/](https://pypi.python.org/pypi/SpeechRecognition/) or speech [http://code.activestate.com/recipes/579115-recognizing-speech-speech-to-text-with-the-python-/](http://code.activestate.com/recipes/579115-recognizing-speech-speech-to-text-with-the-python-/)
* For OCR, try the pytesseract library
* For anything else, you’ll have to search for a library: [http://www.file-extensions.org/filetype/extension/name/text-files](http://www.file-extensions.org/filetype/extension/name/text-files) can help with text file extension names. 

## Counting: Bag of Words

`from sklearn.feature_extraction.text import CountVectorizer`

`count_vect = CountVectorizer()`

`word_counts = count_vect.fit_transform([sipatext])`

`print('{}'.format(word_counts))`

`print('{}'.format(count_vect.vocabulary_))`

It’s possible to process text as sentences, but it’s more useful to separate it into individual words.  The most common way to compare text from documents, tweets etc is to create a Bag of Words: a list of all the words in a text, and how many times each of them appears in it.

The scikit-learn library has some powerful text processing functions, including this one \(CountVectorizer\) to separate text into words. 

## Counting: sets of words

Pairs  \(or triples, 4s etc\) of words

Also: pairs etc of characters, e.g. \[‘mor’, ‘ore’, ‘re ‘, ‘e t’, ‘ th’, ‘tha’, ‘han’\]

Know your Ns:

* ‘Unigram’ == 1-gram
* ‘Bigram’ == 2-gram
* ‘Trigram’ == 3-gram

`count_vectn = CountVectorizer(ngram_range =(2, 2))`

Another approach is to look not at individual words, but at sets of characters \(unigram=1 character, bigram=2 characters; trigram=3 characters, n-gram=n characters\) or words \(also known as word n-grams\).  CountVectoriser has a parameter, ngram\_range, that tells it which sets of words to use \(ngram\_range=\(x,y\) will give you all the n-grams from x to y, e.g. \(1,2\) will give you unigrams and bigrams together\).

NB The same word \(n-gram\) is used for both characters and words, so if someone says n-gram, check which algorithm they’re using. 

## Stopwords

`count_vect2 = CountVectorizer(stop_words='english')`

`word_counts2 = count_vect2.fit_transform([sipatext])`

Stopwords are common words \(“the”, “a”, “and”\) that don’t add to meaning, and might confuse outputs. The CountVectorizer parameter stop\_words tells it which set of stopwords to remove \(e.g. English, French etc\). 

## Term Frequencies

* TF: Term Frequency:
  * word count / \(number of words in this document\)
  * “How important \(0 to 1\) is this word to this document”?
* IDF: Inverse Document Frequency
  * 1 / \(number of documents this word appears in\)
  * “How common is this word in this corpus”?
* TFIDF: 
  * TF \* IDF

From [http://stevenloria.com/finding-important-words-in-a-document-using-tf-idf/](http://stevenloria.com/finding-important-words-in-a-document-using-tf-idf/)

* If a word appears frequently in a document, it's important. Give the word a high score.
* But if a word appears in many documents, it's not a unique identifier. Give the word a low score.

  


