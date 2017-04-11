# Text Analysis

There are a bunch of other things that we can do with bags of words. Here are some of them.

## Natural Language Processing

\* Understanding the grammar and meaning of text

● Useful for, e.g. translation between languages

● Python library: NLTK

## Getting Started With NLTK

`import nltk`

`nltk.download()`![](/assets/Screen Shot 2017-04-11 at 6.54.43 AM.png)

You need to download a bunch of dictionaries etc before you can use the NLTK library.  You do this with the nltk.download\(\) command \(you only need to do this once\).   NLTK.download\(\) will create this pop-up box.  Click on “book”, then “download” to get the standard set of files.

## Get text ready for NLTK processing

`from nltk import word_tokenize`

`from nltk.text import Text`

`fsipa = open('example_data/sipatext.txt', 'r')`

`sipatext = fsipa.read()`

`fsipa.close()`

`sipawords = word_tokenize(sipatext)`

`textlist = Text(sipawords)`

You still have to do some preprocessing.  This is the set of commands to convert raw text into an input ready for NLTK’s algorithms.

## NLTK: Concordance

`textlist.concordance(‘school’)`

`textlist.similar('school')`

`textlist.common_contexts(['school', 'university’])`

Concordance shows you how words occur together, e.g. you can look at this context \(above\) or look for words used in similar context \(textlist.common\_contexts\).

![](/assets/Screen Shot 2017-04-11 at 6.55.03 AM.png)

## NLTK: Word Dispersion Plots

`from nltk.book import *`

`text2.dispersion_plot(['Elinor', 'Willoughby', 'Sophia’])`

Word dispersion plots are a useful way to see where specific words appear in a text.  NLTK comes with a set of example texts, including Austen’s Sense and Sensibility, used here to show where three main characters are mentioned.

![](/assets/Screen Shot 2017-04-11 at 6.59.01 AM.png)

## NLTK: Word Meanings

`from nltk.corpus import wordnet as wn`

`word = 'class'`

`synset = wn.synsets(word)`

`print('Synset: {}\n'.format(synset))`

`for i in range(len(synset)):`

`   print('Meaning {}: {} {}'.format(i, synset[i].lemma_names(), synset[i].definition()))`

NLTK also lets you look up the set of synsets: meanings for an individual word.

## NLTK: Synsets

![](/assets/Screen Shot 2017-04-11 at 6.55.11 AM.png)  
Here's the synset for the word “class”.

## NLTK: Converting words into logic

`from nltk import load_parser`

`parser = load_parser('grammars/book_grammars/simple-sem.fcfg', trace=0)`

`sentence = 'Angus gives a bone to every dog'`

`tokens = sentence.split()`

`for tree in parser.parse(tokens):`

`   print(tree.label()['SEM’])`

And NLTK lets you convert sentences into logical statements that can be used in Artificial Intelligence programs.

More than you ever wanted to know about parsing sentences is here:

* http://www.nltk.org/howto/featgram.html
* Simple\_sem is a simple grammar, just for teaching: its whole specification is at https://github.com/nltk/nltk\_teach/blob/master/examples/grammars/book\_grammars/simple-sem.fcfg



