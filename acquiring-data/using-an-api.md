# Using an API

One way to obtain data is through an application programming interface \(API\).

An API is a way for one computer application to ask another one for a service.  The service is usually "give me this data", but might also be "add this to your datasets".  You can learn more about open APIs at [https://en.wikipedia.org/wiki/Open\_API](https://en.wikipedia.org/wiki/Open_API)

## RESTful APIs

REST = Representational State Transfer; a human-readable way to ask APIs for information.

[http://api.worldbank.org/countries/all/indicators/SP.RUR.TOTL.ZS?date=2000:2015&format=csv](http://api.worldbank.org/countries/all/indicators/SP.RUR.TOTL.ZS?date=2000:2015&format=csv)

THis is a RESTful URL \(web address\); you can type it directly into an internet browser to get a datafile. The URL has 3 parts to it:

* The base url, api.worldbank.org
* a description of what you’re looking for - in this case, 
   countries/all/indicators/SP.RUR.TOTL.ZA, the total rural population for all countries in the world

* Some more details, including filters \(e.g. date=2000:2015 to get only data between 2000 and 2015\) and data formats \(e.g. format=csv\).

Try this address in your browser. Try “&format=json” instead of “&format=csv” at the end, to see the json version of this data. 

## Getting data with Curl

`curl -X GET <URL>`

Curl is a command-line program for transferring files between computers \(e.g. from the server with the datafile you want, and the computer you’re working on now\). For example, the curl command for the World Bank files we just grabbed is

`curl -X GET http://api.worldbank.org/countries/all/indicators/SP.RUR.TOTL.ZS?date=2000:2015`

This will print the contents of that csv file to your screen. A more useful thing to do is to send the data you got from the other server to a file, e.g. using

`curl -o mynewfile.xml -X GET http://api.worldbank.org/countries/all/indicators/SP.RUR.TOTL.ZS?date=2000:2015`

NB You do need to use uppercase for “-X GET” and lowercase for “-o” or this command won’t work. See http://www.compciv.org/recipes/cli/downloading-with-curl/ and https://curl.haxx.se/docs/manpage.html for more details.



