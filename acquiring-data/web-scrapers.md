# Web Scrapers

Sometimes, you’ll want to get datasets that are online, either embedded as tables in webpages, or part of the webpages themselves \(looking at you, UNICEF country data pages!\).

![](/assets/Screen Shot 2017-03-26 at 9.27.23 AM.png)

Web scraping is the process of extracting data from webpages.

If you open a webpage \(e.g. https://en.wikipedia.org/wiki/List\_of\_U.S.\_states\_and\_territories\_by\_population\) and click on “view source”, you’ll see the view that a computer has of that page \(above is the source for the Wikipedia page on US states and territories\). This is where the data is hiding…

## Design First!

Building webscrapers takes time. Start by thinking about exactly what you want to get out of this. Well, start by asking if the dataset’s available in machine-readable form somewhere else, but after that, think about what exactly you want...

What do you need to scrape?

* Which data values
* From which formats \(html table, excel, pdf etc\)

Do you need to maintain this?

* Is dataset regularly updated, or is once enough?
* How will you make updated data available to other people?
* Who could edit your code next year \(if needed\)?

## Using Google Spreadsheets

If you just want one table, then open a google spreadsheet and put this text into cell A1:

`=importHtml("http://en.wikipedia.org/wiki/List_of_U.S._states_and_territories_by_population", "table", 2)`

The pattern for this is: "=importHtml\(“your-weburl”, “table”, yourtablenumber\)".  More on this at: www.mulinblog.com/basic-web-scraping-data-visualization-using-google-spreadsheets/

## Web scraping in Python

You’ve already used the Requests library to grab data from the web. Here's the rest of the toolkit:

* Webpage-grabbing libraries:

* * requests
  * mechanize
  * cookielib

* Element-finding libraries:

* * beautifulsoup
  * lxml.html
  * cssselect

Mechanise and Cookielib help deal with some of the extra information that gets passed between computers \(like cookies and session tokens\); once you’ve downloaded the contents of a webpage, you can use element-finding libraries to find and read the contents of html tags inside it \(e.g. tables, headings, labelled paragraphs of text\).

## Unpicking HTML with Python

`import requests`

`from bs4 import BeautifulSoup`

`url = "https://en.wikipedia.org/wiki/List_of_U.S._states_and_territories_by_population”`

`html = requests.get(url)`

`bsObj = BeautifulSoup(html.text)`

`tables = bsObj.find_all('table’)`

`tables[0].find("th")`

Here’s a small piece of web scraping code. It downloads the page that we just accessed with a Google Spreadsheet, then uses the BeautifulSoup library to find all the tables in it, then the header row in the first table.  Most web scraping code is much much longer than this.



