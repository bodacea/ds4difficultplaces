# Cleaning With OpenRefine

  
OpenRefine is a powerful data cleaning tool. It doesn’t do the cleaning for you, but it does make doing repeated tasks much much easier.  
![](/assets/Screen Shot 2017-04-01 at 9.07.30 PM.png)

This is file 2009\_2013\_popstats\_PSQ\_POC.csv from https://github.com/bodacea/datascienceforbeginners/tree/master/Notebooks/example\_data.   We'll be using this as our example file to clean. 

* Download and install OpenRefine, then click on the OpenRefine icon. This will start a webpage for you, at URL 127.0.0.1:3333
* Click on create project, then select a file. Click “next”. 
* Selected file Notebooks/example\_data/2009\_2013\_popstats\_PSQ\_POC.csv

Now I can see a preview of the data as it will be fed into the system, and a set of buttons for changing that import. And it’s a mess. OpenRefine has put all the data into one column - it’s ignored the commas that separate columns, and it’s used the first row \(which is a comment about the file\) as the column headings.

Fortunately, OpenRefine has ways to start cleaning as you import the file. 

* Select “commas” as the column separators
* Tell OpenRefine to ignore the first 4 lines in the file.
* Then click on “create project”.

And now you have your data. You can do many things with this: clean text en-masse, move columns around \(or add and delete columns\), split or merge data in columns. We’ll play with just a few of these things. Starting with cleaning up those annoying “\*”s in the data.

If you right-click on a cell that you want to change, a little blue “edit” box will appear. 

* Right-click on a cell with a "\*" in it, then edit the box that appears \(in this case, remove the star\). 

Now a powerful thing happens. You can apply whatever you did to that cell, to all other identical cells in this column. So if I want to remove cells with ‘\*’ in them, I click on one of them, edit out the star, then click on “apply to all identical cells”.

* Click on "apply to all identical cells"

And your data is cleaned up. 

## Facets

Facets are also really powerful ways to look at and edit the data in cells. For instance, if you click on the arrow next to “column 3”, you’ll get a popup menu. Click on “facet” then “text facet”, and a facet box will appear on the left side of the screen. Now, if you want to change every instance of “Viet Nam” to “Vietnam”, you just need to edit the text here \(hover over the word “Viet Nam” and an “edit” box will appear. 

If you have really messy inputs, you can cluster them \(see the “cluster” button?\) into similar fields, and assign the text that should replace everything in the cluster. This is a useful way to deal with spelling variations, misspellings, spaces etc.

When you’re finished, click “export” \(top right side of the page\) to write your data out to CSV etc.

I’ve just shown you some of OpenRefine’s power. There’s more: for example, there are a bunch of OpenRefine recipes at [https://github.com/OpenRefine/OpenRefine/wiki/Recipes](https://github.com/OpenRefine/OpenRefine/wiki/Recipes)



