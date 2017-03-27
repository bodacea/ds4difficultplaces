# D3 and Beyond

  
You’ve met matplotlib and tableau, but you also need to know about some of the more powerful visualisation tools. One of these is D3: it’s used widely, but takes a while to explain, so we’re jstu going to cover how to run a D3 file.

For more details on D3, look in my github account for an earlier course that included D3 \(https://github.com/bodacea/datasciencecodingfordevelopment\) – or better yet, get Scott Murray’s book on it \(http://alignedleft.com/work/d3-book.

# Drawing a Chord Diagram in D3: Online

![](/assets/Screen Shot 2017-03-27 at 7.02.51 AM.png)

* Use the terminal window
* cd to the directory containing file 4.3\_d3\_chord\_online.html
* In the terminal window, type:

python -m http.server 8899 &

* Then go to [http://0.0.0.0:8899/4.3\_d3\_chord\_online.html](http://0.0.0.0:8899/4.3_d3_chord_online.html) in your browser
* And hover your mouse over the circle edges...
* \(to exit, type control-c\)

This starts a webserver on your PC, that you can then go to and look at your D3 file in.

* NB I changed the channel to 8899 because the standard \(8888\) clashes with the ipython notebook server.
* Chord example is from 
  [http://bl.ocks.org/mbostock/4062006](http://bl.ocks.org/mbostock/4062006)
* NB: space in the filename will making your code crash; try to use e.g. underscores instead.

Go ahead and click on the coloured edges of the circle…

## Drawing a Cord Diagram in D3: Offline

* Copy your d3.js.zip file and the 4.4\_d3\_chord\_offline.html file into a directory
* Unzip d3.js.zip
* In the directory your code is in, type:

python -m http.server 8899 &

* Then go to [http://0.0.0.0:8899/4.4\_d3\_chord\_offline.html](http://0.0.0.0:8899/4.4_d3_chord_offline.html) in your browser
* And hover your mouse over the circle edges...
* \(to exit, type control-c\)

The difference between the two files is in where the D3 code comes from. 

* In the online version, the D3 code is at //d3js.org/d3.v3.min.js \(the d3.v3.min.js file is a version of d3.js with all the whitespace and comments taken out to make it smaller\);
* In the offline version, the D3 code is on your pc, in file d3.js the d3 directory.

Bugz: you might get an error message saying “Address already in use”. This is bad and naughty, but to quickly fix it, try:

* in the terminal window, type “ps -a”
* Note the number at the left of the line that looks like “
  7064 ttys000
   0:00.16 python -m http.server 8899”
* type “kill -9 7064” \(or whatever your number was\).
* Note: this is a very powerful command: make sure you’re using the right number, or you might accidentally shut down your machine…

## Communication doesn't have to be Complex ![](/assets/Screen Shot 2017-03-27 at 7.04.12 AM.png)

Visualisations don’t have to be complex to be powerful: here, two numbers are left to speak for themselves. \[image: screenshot from news.bbc.co.uk\]

## Communication doesn't have to be "Standard"

![](/assets/Screen Shot 2017-03-27 at 7.06.29 AM.png)

Visualisations don’t have to be ‘standard’ either: an example of this is Hans Rosling’s videos of poverty changes over time.  \[Image: Hans Rosling video; see https://www.youtube.com/watch?v=jbkSRLYSojo for more on how this was created\]

