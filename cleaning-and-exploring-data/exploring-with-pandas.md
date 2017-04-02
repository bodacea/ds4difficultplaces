# Exploring with Pandas

Pandas is a Python data analysis library that helps you quickly explore and analyse row-column datasets. 

## Reading and writing datafiles with Pandas

`import pandas as pd`

`df = pd.read_stata('example_data/AG_SEC12A.dta')  # read file`

`df.to_csv('mynewcsvfile.csv')  # write data to file`

Pandas has several functions for reading data from files: read\_csv, read\_excel, read\_sql, read\_json, read\_html, read\_stata, read\_clipboard.  It has similar functions for writing data to files, e.g. to\_csv, etc

Read\_sql reads database files; read\_html reads tables from html pages; read\_clipboard reads from your PC’s clipboard.

Warning: if you have more columns of data than you have column headings, Pandas read\_csv can fail. If this happens, there are lots of optional parameters to read\_csv that can help, but in practice it’s better to feed in clean data.

## Eyeballing Rows

How many rows are there in this dataset?

`len(df)`

What do my data rows look like?

`df.head(5)`

`df.tail()`

`df[10:20]`

## Eyeballing Columns

What’s in these columns?

`df[‘sourceid’]`

`df[[‘sourceid’,’ag12a_01','ag12a_02_2']]`

`df[‘sourceid’].unique()`

How do you filter columns?

`df[df.ag12a_01 == ‘YES’]`

`df[(df.ag12a_01 == 'YES') & (df.ag12a_02_1 == 'NO')]`

## Summarising Columns

What are my column names and types?

`df.columns`

`df.dtypes`

Which labels do I have in this column?

`df['ag12a_03'].unique()`

`df['ag12a_03'].value_counts()`

What are my columns’ mean, standard deviation etc?

`df.describe`

NB df.describe will only find mean and standard deviation for numerical columns - which is reasonable.

## Pivot tables: combining data from one dataframe

`pd.pivot_table(df, index=['sourceid', 'ag12a_03'])`

`pd.pivot_table(df[['sourceid','ag12a_03','count']], index=['sourceid', 'ag12a_03'], aggfunc='sum')`

This is very similar to the pivot tables in Excel. More at [http://pbpython.com/pandas-pivot-table-explained.html](http://pbpython.com/pandas-pivot-table-explained.html)

Those NaNs? “Not a numbers”.

## Merge: combining data from multiple dataframes

`popstats = pd.read_csv('example_data/cleaned_popstats.csv')`

`longnames = pd.DataFrame({ 'country' : pd.Series(['United States of America', 'Zaire', 'Egypt']),`

`'longname' : pd.Series([True, True, False])})`

`merged_data = pd.merge(`

    `left=popstats,`

    `right=longnames,`

    `left_on='Country/territory of residence',`

    `right_on='country')`

`merged_data[['Year', 'Country/territory of residence', 'longname', 'Total population', 'Origin / Returned from']]`

Pandas merge defaults to an ‘inner join’: only keep the rows where data exists in \*both\* tables. More details in e.g. [http://www.datacarpentry.org/python-ecology/04-merging-data](http://www.datacarpentry.org/python-ecology/04-merging-data)

## Left Joins: Keep everything from the left dataframe

`longnames = pd.DataFrame({ 'country' : pd.Series(['United States of America', 'Zaire', 'Egypt']),`

` 'longname' : pd.Series([True, True, False])})`

`merged_data = pd.merge(`

` left=popstats,`

` right=longnames,`

` how='left',`

` left_on='Country/territory of residence',`

` right_on='country')`

`merged_data[['Year', 'Country/territory of residence', 'longname', 'Total population', 'Origin / Returned from']]`

  
Left join: keep all rows from the first table; combine rows where you can, put “NaN”s in the rows when you can’t.

Some great visuals about joins: [http://www.codeproject.com/Articles/33052/Visual-Representation-of-SQL-Joins](http://www.codeproject.com/Articles/33052/Visual-Representation-of-SQL-Joins)

## Normalising Dataframes

You can normalise your tables in Pandas by using the stack function - see e.g. [http://pandas.pydata.org/pandas-docs/stable/reshaping.html](http://pandas.pydata.org/pandas-docs/stable/reshaping.html)





