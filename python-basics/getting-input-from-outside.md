# Getting Input From Outside

At some point, we’re going to need to pull data into our code: this might be input from the code’s user, or from a datafile, or from an API \(application programming interface: more on that soon\). Here’s how.

## Getting input from the user

`user_text = input('Give me some text> ')`

`lower_text = user_text.lower()`

`text_length = len(user_text)`

`print('Your text is {}, its length is {}'.format(user_text, text_length))`

You might want to ask the user for input \(e.g. the name of the csv file they want your code to process\). The function “input\(\)” does this.

## If-Then

`user_text = input('What’s your name? ')  
if 'a' in user_text.lower():`

`    print("You've got As: awesome!")`

`else:`

`    print("No As in your name, but still awesome!")`

Sometimes we want to change what a program does, based on the values of some of its variables. To do this, we use conditional \(“if-then”\) statements.

Here, we’re doing one thing if the name you input contains the letter ‘a’, and something different if it doesn’t contain the letter ‘a’.

## Conditional Logic

`user_text = input('What’s your name? ')  
 if user_text.lower() == 'sara':`

`   print('Same name as me!')`

`else:`

`   print('Not the same name as me, but still awesome!')`

Sometimes we’ll want to process only some of the data that we see.  In this case, we’re only interested in people called Sara, so we test to see if the user input is ‘Sara’.  This test \(if a == b\) is called a conditional statement, because running the rows nested below the “if” statement \(“nested” = using another 4 spaces, to show that the “print\(\)” statement belongs to the “if” one\) is conditional on whether the statement “user\_text.lower\(\) == ‘Sara’” is true.  
 The conditions you’ll see in code include:

* a == b: a’s value is the same as b’s value
* a != b: a’s value is not the same as b’s value
* a &lt; b: a is smaller than b
* a &gt; b: a is bigger than b
* a&lt;= b: a is smaller than or equal to b
* a &gt;= b: a is bigger than or equal to b

Beware the “==” in a conditional statement. “==” is used to test similarity;  “=” is used to set the value of the thing on its left to the value of the thing on its right.  Python will let you use either of these in a condition.

## Libraries

First, a brief note about libraries.  Libraries are pieces of code that do something you need, e.g. the CSV library helps you read and write CSV files.  To include a library, use this in your code:

`import libraryname`

Places to look for libraries include:

* https://docs.python.org/3/library/ \(you already have these\)
* https://pypi.python.org/pypi

## Reading a CSV file with the Pandas Library

`import pandas as pd`

`df= pd.read_csv('citibike/citibikeextract.csv')`

`print('{}'.format(df))`

`print('{}'.format(df['gender'].value_counts()))`

Let’s read a CSV file.  You’ll meet the Pandas library in detail later: it’s designed for doing data science tasks, including reading in large datafiles in many different formats.

You might be wondering why I don’t just read this file into Microsoft Excel. I tried this earlier: Excel has a limit on the number of rows it can read in and process, and only read 1,048,575 rows of the 1,085,676 available; python doesn’t have this limit, and read in all the rows of data. Beware: when you read large datasets, be sure that you get all the data in them!

## Getting input from a dirty CSV file

`import csv`

`fin = open('example_data/ebola-data-db-format.csv', 'r')`

`csvin = csv.reader(fin)`

`headers = next(csvin)`

`for row in csvin:`

` print(‘{}’.format(row))`

`fin.close()`

Sometimes you’ll need to read in a CSV file the non-Pandas way \(e.g. because it’s been corrupted and has commas in places it shouldn’t\).Here, we’re using the Python library “CSV” to read in the contents of a CSV file.

* First, we need to tell our code to use the CSV library \(“import CSV”\)
* Then we tell it which file to open \(“open\(\)”\), and that we’re reading from \(not writing to\) a file \(“‘r’”\).
* We’ve opened the file for input, but that’s not enough if we want to treat this file as a CSV file \(instead of a text file, or Excel, json, xml etc\).  To do this, we create a CSV reader object, using “csv.reader\(\)”.  This object \(that we’ve called “csvin”\) knows about commands like “next\(\)” \(get me the next row of data from the csv, and put it into a list object\), and that “for row in csvin” will loop over each remaining row in the CSV file, and input it as a list.
* The rest is grabbing each row in the CSV file, and printing out that row.   At this point, we could discard or modify the corrupted rows, and write the modified rows back to a new, ‘clean’ file.
* When you’re done, fin.close\(\) closes the link between this program and the file pointed at by the variable ‘fin’.

In other sessions, you'll see shorter, ways to read in a CSV file \(e.g. using dictreader or pandas.read\_csv\), but this is development data, and the CSV library can often read in difficult CSV files that other methods fail on.



