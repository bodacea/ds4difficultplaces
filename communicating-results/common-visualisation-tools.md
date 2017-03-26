# Common Visualisation Tools

There are many visualisation tools available: this is just a set of more-common tools that are free or can be used offline.

## Choosing a Visualisation Tool

* What do you want to do?

* * Standard visualisations, or something special?
  * Inputs: files \(e.g. CSV\) or streaming data?
     Maps?
  * Non-roman languages \(Arabic, Mandarin etc\)?
  * Interactive or static?
* Where do you want to do it?
* * Online or offline?
* Any other restrictions?
* * Third-party visible or private?
  * Free, cheap or expensive?
  * Ease of use \(and support!\)

Again, design. Not all tools are created equal: if you want to create offline Sankey diagrams in Arabic, the toolset available will be much smaller than for a static barplot in English. Here are some things you should think about when you choose a tool to use.

## Excel

![](/assets/Screen Shot 2017-03-26 at 7.02.48 PM.png)

* Limited set of visualisation types
* Not interactive
* Offline
* Static
* Not free
* Relatively easy
* Widely used

To create this chart: copied the asylum seeker data into an excel spreadsheet. Created a pivot table from the data. Created a chart from the pivot table. Did lots of fussing around to get chart elements in the right place/ filtered. Still more fussing needed to get e.g. the legend right.

## Matplotlib

![](/assets/Screen Shot 2017-03-26 at 7.04.28 PM.png)

* Python visualisation library
* Not interactive
* Not the prettiest \(but does have ways to make it prettier, e.g. Seaborn\)
* Good for quick-and-dirty views of data
* Offline + Online
* Free

## Tableau

![](/assets/Screen Shot 2017-03-26 at 7.05.22 PM.png)

Tableau Public

* Free
* Interactive
* Excel or text \(CSV\) import only
* Public, and needs internet connection

Tableau Desktop

* Not free \(but free to students who ask\)
* Interactive
* Range of import formats and datastore APIs
* Private, and works offline

## D3

![](/assets/Screen Shot 2017-03-26 at 7.06.17 PM.png)

* Free
* Interactive
* Very very flexible = almost any diagram you want
* Steep learning curve
* Works offline

## Other Common Tools

![](/assets/Screen Shot 2017-03-26 at 7.07.26 PM.png)

* Piktochart
* Google fusion tables
* Ggplot
* Highcharts
* NVD3

The image is one of the Piktochart templates. Infographics aren’t immediate outputs from python code, but can be very powerful.





