# Tableau Exercise

Now let's plot something in Tableau.

## The result: Stacked Column Chart![](/assets/Screen Shot 2017-03-27 at 6.47.15 AM.png)

This is what we’re going to create, using the asylum-seeker dataset.

## Import data into Tableau![](/assets/Screen Shot 2017-03-27 at 6.49.13 AM.png)

Get a copy of example file “cleaned\_popstats.csv” from https://github.com/bodacea/datascienceforbeginners/blob/master/Notebooks/example\_data/cleaned\_popstats.csv 

* Open Tableau Public \(click on the executable\)
* Click on “Text File”
* Select “cleaned\_popstats.csv”, then “open”
* Congratulations - you’ve got data into Tableau
* Now click on “sheet 1” at the bottom of the page

## Add Rows![](/assets/Screen Shot 2017-03-27 at 6.50.34 AM.png) 

From sheet1:

* You should see a “show me” box on the top RHS: click on it, then the thing that looks like a column chart \(sigh: Tableau calls it “stacked bar”\)
* Drag “asylum seekers” from under “Measures” to the “rows” box
* Don’t panic when “asylum seekers” becomes “SUM\(Asylum seekers\)” in the Rows box. This is normal.

## Add Columns![](/assets/Screen Shot 2017-03-27 at 6.51.46 AM.png)

* Drag “origin/ returned from” from under “dimensions” to the “columns” box
* Right-click on “origin/returned from” in the “columns” box.
* Click “sort…”
* Click “descending”
* Click “field”
* Click “okay”

At this point, you’re probably wondering why the columns are so small

## Remove a column from the graph

![](/assets/Screen Shot 2017-03-27 at 6.53.05 AM.png)

* Right-click on “various” in the graph.
* Click “Exclude”
* Watch the graph scale to the new biggest value \(Democratic Republic of the Congo\)

## Add Colours ![](/assets/Screen Shot 2017-03-27 at 6.55.50 AM.png)

* Drag “Year” to color \(under “Marks”\)![](/assets/Screen Shot 2017-03-27 at 6.56.16 AM.png)

The green is okay, but not easy to read; here’s how you get a set of different colours in your bars.

* Click the little triangle that appears when you hover over the new “Year” colours box
* Click “Edit colors”
* Click “stepped color”
* Click the bar under “Palette”; click “Red Blue Diverging” then “okay”

## The result: A stacked column chart![](/assets/Screen Shot 2017-03-27 at 6.57.35 AM.png) 

Also available at [https://public.tableau.com/profile/publish/DS\_session\_example/Sheet1\#!/publish-confirm](https://public.tableau.com/profile/publish/DS_session_example/Sheet1)









