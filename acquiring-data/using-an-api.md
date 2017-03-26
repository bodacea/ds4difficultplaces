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

Try this address in your browser. Try “&format=json” or "&format=xml" instead of “&format=csv” at the end, to see the json version of this data.  Many APIs will only return XML data; some will return XML and JSON; others, like this one, will return XML, JSON, CSV and often other formats too.

## Getting data with Curl

`curl -X GET <URL>`

Curl is a command-line program for transferring files between computers \(e.g. from the server with the datafile you want, and the computer you’re working on now\). For example, the curl command for the World Bank files we just grabbed is

`curl -X GET http://api.worldbank.org/countries/all/indicators/SP.RUR.TOTL.ZS?date=2000:2015`

This will print the contents of that csv file to your screen. A more useful thing to do is to send the data you got from the other server to a file, e.g. using

`curl -o mynewfile.xml -X GET http://api.worldbank.org/countries/all/indicators/SP.RUR.TOTL.ZS?date=2000:2015`

NB You do need to use uppercase for “-X GET” and lowercase for “-o” or this command won’t work. See [http://www.compciv.org/recipes/cli/downloading-with-curl/](http://www.compciv.org/recipes/cli/downloading-with-curl/) and [https://curl.haxx.se/docs/manpage.html](https://curl.haxx.se/docs/manpage.html) for more details.

## The Python Requests Library

`import requests`

`import json`

`worldbank_url = "http://api.worldbank.org/countries/all/indicators/SP.RUR.TOTL.ZS?date=2000:2015&format=json"`

`r = requests.get(worldbank_url)`

`jsondata = json.loads(r.text)`

`print(jsondata[1])`

The Python requests library is useful for calling APIs from a python program \(e.g. so you can then use or save the information returned from them\). You’re maybe wondering how to get this json data into a file. Here’s the code for that:

`import json`

`fout = open('mynewdata.json', 'w')`

`json.dump(jsondata, fout)`

When you request data from a server, it sends back a code telling you about any problems it had with your request. To see this, type`r.status_code`.  Some common values for r.status\_code are:

* 200: okay
* 400: bad request
* 401: unauthorised
* 404: page not found

Most of the time, you’ll see 200, which means everything’s okay; if you see 400 or 404, look for errors in the URL you’re using; if you get 401, check to see if you need a password to access this API. See https://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html for more details.

`import requests`

`r = requests.get('https://api.github.com/user', auth=('yourgithubname', ‘yourgithubpassword'))`

`dataset = r.text`

If the API needs a username and password \(as github does\), here’s how to format your request. This code won’t work without a valid username and password: if you cut and paste it, and substitute your own github username and password \(which in itself might be a good excuse to get a github account\), it should.



