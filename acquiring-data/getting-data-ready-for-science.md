# Getting Data Ready for Science

## Changing data formats

Most data science and visualisation programs can read CSV data, so if you can easily convert data to that, good. There are websites that will convert to csv; you can also do this by reading data in one format, and writing it out in another.

`import pandas as pd`

`df = pd.read_json(“myfilename1.json”)`

`df.write_csv(“myfilename2.csv”)`

The Pandas library is very helpful for reading in one format, and writing in another, if the data is row-column.

## Normalising Data

![](/assets/Screen Shot 2017-03-26 at 9.36.01 AM.png)We’ll cover data cleaning later, but if you want to try the next chapter's visualisation techniques on your own data, it will need to at least be normalised. Here’s what we mean by this \(and Tableau has a tool for doing this: see http://kb.tableau.com/articles/knowledgebase/denormalize-data\).



