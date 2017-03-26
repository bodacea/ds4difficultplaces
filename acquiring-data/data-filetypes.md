# Data Filetypes

There are many datafile types - here’s a guide to some of them.  A basic taxonomy is: 

* Structured data:
* * Tables \(e.g. CSVs, Excel tables\)
  * Relational data \(e.g. json, xml, sqlite\)

* Unstructured data:
* * Free-text \(e.g. Tweets, webpages etc\)

* Maps and images:
* * Vector data \(e.g. shapefiles\)
  * Raster data \(e.g geotiffs\)
  * Images

Tables typically have rows and columns; relational data is typically hierarchical, e.g. can’t be easily converted into row-column form.

## Reading Datafiles into Python

We'll meet the Pandas library soon: it's basically used to manipulate row-column data, and has a set of functions for reading in different datatypes, including: 

* `read_csv()`
* `read_excel()`
* `read_json()`
* `read_stata()`
* `read_sql()`
* `read_html()`
* `read_clipboard()`

Read\_sql reads database files; read\_html reads tables from html pages; read\_clipboard reads from your PC’s clipboard.

Beware: if you have more columns of data than you have column headings, Pandas read\_csv can fail. If this happens, there are lots of optional parameters to read\_csv that can help, but in practice it’s better to feed in clean data.

Using one of these looks like this: 

`import pandas as pd`

`df = pd.read_stata('example_data/AG_SEC12A.dta') `

\(this code reads from a Stata formatted file, and puts the data in it into a variable called df\). 

## Reading datafiles into Tableau

You can read CSV, Excel and OData files into Tableau Public.  If you're using CSV or Excel: 

* Start your data in cell A1

* Have the first row be the column headers

* Have every subsequent row be one piece of data

Odata is the Azure Marketplace connector.\(https://onlinehelp.tableau.com/current/pro/online/mac/en-us/examples\_odata.html\). 

## CSV files

CSVs are the workhorse of datatypes: almost every data application can read them in. They look like this:

* Comma-separated values
* Lots of commas
* Sometimes tab-separated \(TSVs\)

## JSON

* JavaScript Object Notation
* Lots of braces { }
* Structured, i.e. not always row-by-column
* Many APIs output JSON
* Not all applications read JSON

JSON files are hierarchical, e.g. you usually can't easily convert them into row-column form.  If you have an application that only takes CSV files, you can convert by either writing some Python code to do this, or using a conversion website \(e.g. [http://www.convertcsv.com/json-to-csv.htm](http://www.convertcsv.com/json-to-csv.htm)\)

## XML

  
li.li1 {margin: 0.0px 0.0px 0.0px 0.0px; font: 21.0px Arial; color: \#000000; -webkit-text-stroke: \#000000}  
span.s1 {font: 12.0px Helvetica; color: \#000000; -webkit-text-stroke: 0px \#000000}  
span.s2 {font-kerning: none; font-variant-ligatures: no-common-ligatures}  
span.s3 {font: 12.0px Helvetica; color: \#000000}  


* eXtensible Markup Language
* Lots of brackets &lt;&gt;
* Structured, i.e. not always row-by-column
* Some applications read XML
* HTML is a form of XML

XML, like JSON, is hierarchical.  If you need to convert to CSV, you'll either have to write some code to do this, or use a conversion website \(e.g. http://www.convertcsv.com/xml-to-csv.htm\)







