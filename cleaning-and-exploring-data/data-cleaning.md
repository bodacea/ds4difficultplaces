# Data Cleaning

Data cleaning is the process of removing errors \(spelling mistakes, extraneous characters, corrupted data etc\) from datafiles, to prepare them for use in algorithms and visualisation. Data cleaning is sometimes also called data scrubbing or cleansing.

Algorithms want their data to be: 

* Machine-readable
* Consistent format \(e.g. text is all lowercase\)
* Consistent labels \(e.g. use M/F, Male/Female, 0/1/2, but not \*all\* of these\)
* No whitespace hiding in number or text cells
* No junk characters
* No strange outliers \(e.g. 200 year old living people\)
* In vectors and matrices
* Normalised \(each datapoint has its own row in the data matrix.\)

You'll spend a lot of your time cleaning and exploring data. Some people will tell you that's unnecessary drudge work, but what it really is, is making friends with your data; understanding it yourself before you run any algorithms \(e.g. machine learning algorithms\) on it.  Do this because a\) it’s hard to run algorithms on badly-formatted data, and b\) discovering data issues when you’re trying to train a classifier sucks - you have enough on your hands without dealing with outliers and spelling errors too.

Get to know your dataset, before you ask a machine to understand it.

* Eyeball your dataset
* Get the basics statistics \(mean, sd etc\) of your data
* Understand how data columns interact
* Clean your data
* Plot your data \(visually look for trends and outliers\)
* Do more cleaning if you need to \(e.g. those outliers\)



