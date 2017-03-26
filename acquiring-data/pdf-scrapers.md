# PDF Scrapers

A lot of development data gets delivered in PDFs. Not as much as it used to, but it will happen to you, and it’s worth knowing how to get at the data in a PDF without typing everything in by hand.

Scraping is the art of converting data in files and webpages that’s easy for humans to read, but difficult for machines.  Try to avoid scraping unless you have to:

* * Small dataset: type it in!
  * Larger dataset: Look for datasets and APIs online

Here are places to look for the data before you write a scraper:

* the website that data’s in, for file copies of the data
* the website that data’s in, for an api \(http://api.theirsitename.com/, 
  [http://theirsitename.com/api](http://theirsitename.com/api)
  , Google “site:theirsitename.com api”\)
* related sites for file copies and apis
* Community warehouses \(scraperwiki.com, datahub.io etc.\) for other peoples’ scrapers

![](/assets/Screen Shot 2017-03-26 at 9.20.29 AM.png)

  
Development data is often in big PDFs \(the image above is from an 80-page PDF containing Tanzania 2012 population data\)  And we’ll need to get the data out of them. This is where PDF scrapers come in. 

A PDF scraper is an application that converts PDF files into text or tables. Some, but not all, PDFs can be scraped.  To see if your file can: 

* Open the PDF file in Acrobat
* Can you cut-and-paste text in the file?
* * Y:
  * * use a PDF scraper
  * N:
  * * You could try OCR \(Optical Character Recognition\)
    * But you’ll probably have to type text in, or use TurkSourcing

Here are some of the PDF scrapers available. 

* Cut and paste to Excel
* Tabula: free, open source, offline
* Pdftables: not free, online
* CometDocs: free, online

If you have a single-page table in a PDF file, try selecting all the table, then pasting it into cell A1 of an Excel spreadsheet. For anything larger, try one of the applications above \(it's possible to scrape PDFs using low-level programs like PDFbox, but you'll spend a lot of time maintaining your scraper code if you do that\). 



