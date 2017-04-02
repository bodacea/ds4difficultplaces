# Cleaning with Python

## Cleaning Strings

You''ll spend a lot of time cleaning up text. Mostly this is because:

A\) although you see 'Capital' and 'capital' as the same words, an algorithm will see these as different because of the capital letter in one of them

B\) people leave a lot of invisible characters in their data \(NB they do this to string representations of numerical data too - and many spreadsheet programs will store numbers as strings\) - this is known as "whitespace", and can really mess up your day because "whitespace" and "whitespace " look the same to you, but an algorithm will see as different.

### Removing capital letters and whitespace

`mystring = " CApiTalIsaTion Sucks ”`

`mystring.lower().strip()`

Original text is “`CApiTalIsaTion Sucks `“; lowercase is: “` capitalisation sucks `“. Strip\(\) removes both leading and trailing spaces. The output you should see is “`capitalisation sucks`”, i.e. lowercase with no spaces at the start and end of the string. 

### Using regular expressions for more complex cleaning

`import re`

`re.sub(r'\s', '.', 'this  is  a string')`

You probably didn't notice it, but there's a repeated space in "capitalisation  sucks".  That kind of thing \(invisible to the naked eye\) can really mess up your day.  Use the RE \(regular expression\) library to clean up strings. To use a regular expression \(aka RegEx\), you need to specify two patterns: one input pattern that will be applied repeatedly to the input text, and one output pattern that will be used in place of anything that matches the input pattern. 

Regular expressions can be very powerful and can take a while to learn, but here are a couple of patterns that you’ll probably find helpful at some point; [http://rubular.com](http://rubular.com/)/is a great place to play around with these.

^\w = everything that isn’t a character or number.

\[\] = a group of possible characters, e.g. \[^\w \] = alphanumeric plus space.

\s+,\s+ = one or more spaces followed by a comma then one or more spaces. Let's try that:

`import re`

`string1 = "This is a! sentence&& with junk!@"`

`print('{}'.format(re.sub(r'[^\w]', '', string1)))`

You should see cleaned-up text, e.g. "This is a sentence with junk"

## Cleaning Dates and Times

European vs American? Name of month vs number? Python comes with a bunch of date reformatting libraries that can convert between these. For example:

`import datetime`

`date_string = “14/03/48"`

`datetime.datetime.strptime(date_string, ‘%m/%d/%y').strftime('%m/%d/%Y')`

More about date formats in [https://docs.python.org/3/library/datetime.html](https://docs.python.org/2/library/datetime.html)

