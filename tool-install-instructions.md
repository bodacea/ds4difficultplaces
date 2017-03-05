# Tool Install Instructions

These are the tools that you need to install before each lab. If you have problems, Sara can be reached on Skype at: sj.farmer \(I get a lot of junk requests: when you connect, add a note that you're doing these sessions\).

If you want to install and play with tools ahead of time, please feel free: most of them are a great deal of fun.

## Session: Python Basics {#h.dsk3vnwdsy7i}

You need to know where your terminal window is, and install Python, R and iPython. You'll also need to install github to get the latest version of the code examples.  Instructions for all this are below.

### 1. Make friends with your terminal window {#h.y5wdh8hnk6wt}

DO THIS:

* Find your terminal window.  Your terminal window is here:

* Mac: applications 
  &gt;
   utilities 
  &gt;
   terminal
* Windows: Taskbar Start Button 
  &gt;
   Command Prompt
* Linux: applications 
  &gt;
   accessories 
  &gt;
   terminal

* Type "ls" \(mac/linux\) or "dir" \(windows\) in it.



Mac Users: your terminal commands include:

* pwd: print current directory name
* cd xxx: change to directory xxx
* cd ~: go to your ‘home’ directory
* ls: list files in directory
* ls -al: list all files in directory \(including hidden ones\)
* mkdir xxx: create a directory called xxx
* \(see
  [https://github.com/0nn0/terminal-mac-cheatsheet/wiki/Terminal-Cheatsheet-for-Mac-\(-basics-](https://www.google.com/url?q=https://github.com/0nn0/terminal-mac-cheatsheet/wiki/Terminal-Cheatsheet-for-Mac-\(-basics-&sa=D&ust=1463755268740000&usg=AFQjCNFHMVeTGNMdF33wYDti10eJpAOzow)
  \) for more\)



Windows users: your Terminal commands include:

* dir: print current directory name and list files in directory
* cd xxx: change to directory xxx
* cd ~: go to your ‘home’ directory
* mkdir xxx: create a directory called xxx
* \(see
  [http://www.cs.princeton.edu/courses/archive/spr05/cos126/cmd-prompt.html](https://www.google.com/url?q=http://www.cs.princeton.edu/courses/archive/spr05/cos126/cmd-prompt.html&sa=D&ust=1463755268742000&usg=AFQjCNENXQWPN8MojwhLYFOYlERJE62E7Q)
   for more\)

### 2. Install Python, iPython and Python libraries {#h.3s2kau5963ou}

DO THIS:

* Install the Python 3.5 version of Anaconda from
  here
  :        
  [https://www.continuum.io/downloads](https://www.google.com/url?q=https://www.continuum.io/downloads&sa=D&ust=1463755268744000&usg=AFQjCNHoUjyAQgfEMiBMFOPncj84WM4unw)
* IF YOU CHOOSE TO INSTALL MINICONDA, you will need to install these libraries for the course: requests, scikit-learn, nltk, networkx, xlrd, xlwt, scrapy, bs4. To install libraries, go to the terminal window and type "pip install " where ics the library name, e.g. "pip install xlrd"
* Close your current terminal window, and open up a new one.
* In the terminal window, type this series of commands \(some of them will take several minutes to finish. You might want to go make some tea/coffee/beverage of choice whilst they do that\):                

* conda --version
* conda update conda
* pip install --upgrade pip

MAC 10.6 - 10.8 users: you may get the error "Cannot locate working compiler" at this point. Don't panic: we're working on this, and will get a fix to you ASAP.

### 3. Install R {#h.3ttpwju5n6gd}

DO THIS: In the terminal window, type this series of commands:

* conda install -c r r-essentials
* conda update -c r r-essentials

### 4. Install Git {#h.7lz2lwfwurr7}

DO THIS: Get a Github account at[https://github.com/](https://www.google.com/url?q=https://github.com/&sa=D&ust=1463755268747000&usg=AFQjCNGoCc1z57Nz7FBplVDgKvzhVejytw)

NB Some Mac users will get a "can't be opened because it is from an unidentified developer" message when you try to run the Git install file. This is happening because your security doesn't like apps that aren't downloaded from the Mac App Store. The answer is to right-click on the file, or to press control when you click on it.

DO THIS: IF YOU HAVE A MAC WITH OSX Snow Leopard: install git version 1.7.5 from[https://code.google.com/p/git-osx-installer/downloads/list](https://www.google.com/url?q=https://code.google.com/p/git-osx-installer/downloads/list&sa=D&ust=1463755268748000&usg=AFQjCNEUlbgXJs_6gt1VyqrC7SXUEEN6wA)

* If you want to know which version of mac you have, click the apple symbol in the top right hand side of your screen, then "about this mac". If it says "snow leopard" or "version 10.6" then you have Snow Leopard.

DO THIS: IF YOU HAVE A MAC WITHOUT OSX Snow Leopard: Install github from[http://git-scm.com/downloads](https://www.google.com/url?q=http://git-scm.com/downloads&sa=D&ust=1463755268749000&usg=AFQjCNHsKYlNR8uTxn7bbQKls17jJ6KXgw) \(click on the logo for your operating system \(windows, mac etc\) under "downloads"\)

DO THIS: WINDOWS USERS:

* Download the git install file from
  [http://git-scm.com/downloads](https://www.google.com/url?q=http://git-scm.com/downloads&sa=D&ust=1463755268750000&usg=AFQjCNG2dAjmz2oyryyEpUsyC4e426x99Q)
   \(click on the logo for your operating system \(windows, mac etc\) under "downloads"\). Click on this file to start the install.
* On the second install screen, you'll see the option 'Use Git from the Windows command prompt'. Tick this box \(or you'll get "git is not recognized as an internal or external command" when you try to run git\).
* On the third or fourth install screen \("Configuring the git terminal to work with git bash"\), you'll see the option "Use Windows' default console window". Tick this box.

There's helpful material at git-scm.com/book/en/Getting-Started-Installing-Git if you get stuck.

### 5. Test Git {#h.zf50r0zc5pw3}

DO THIS:

* open a new terminal window \(e.g. close the current terminal window, and open up a new one\)
* Check you have git installed by typing "git --version" in the terminal window. You should see something like "git version 2.7.0.windows.1"
* in the terminal window, type "git clone
  [https://github.com/bodacea/inafu6513.git](https://www.google.com/url?q=https://github.com/bodacea/inafu6513.git&sa=D&ust=1463755268753000&usg=AFQjCNHiobSWl48XQ-iuraC7PfW0RyIChQ)
  " This will grab you a copy of the code examples for this course \(we'll be adding to these as the course progresses, which is why we're using git\).

## Session: Acquiring data {#h.j4cuwflf3eqg}

You need to:

* Install Tabula

### 1. Install Tabula {#h.pv1vt4ali0ri}

DO THIS: Go to[http://tabula.technology/](https://www.google.com/url?q=http://tabula.technology/&sa=D&ust=1463755268755000&usg=AFQjCNHAGRwMixgdcbFo-Br6zzTIQYZoOw), click the "download for..." button.

## Session: Visualisation software {#h.71jjblg0qbim}

You need to:

* Get Tableau Public account.
* Install Tableau.

### 1. Install Tableau {#h.om86nwfyy035}

DO THIS:

* Go to
  [http://public.tableau.com/](https://www.google.com/url?q=http://public.tableau.com/&sa=D&ust=1463755268758000&usg=AFQjCNFpMCqA6Gud6mctSxyhYYp27M7Aqw)
   and click “Download The App”
  OR:
  brew cask install tableau-public
* Start Tableau Public \(Mac OSX10.6 users: we know Tableau doesn’t support you. We’re working on it.\)
* Find cleaned\_popstats.csv \(it’s in the Notebooks directory\)
* Optional: install Tableau Desktop

### 2. Set up D3 {#h.cv7u0m2yav3}

DO THIS:

* Go to
  [http://d3js.org](https://www.google.com/url?q=http://d3js.org/&sa=D&ust=1463755268761000&usg=AFQjCNGyTBgS0kYiuG8er9CHLmCzU_POEg)
   and click on “d3.zip”
* Check that you have javascript enabled in your browser:
  [http://www.enable-javascript.com](https://www.google.com/url?q=http://www.enable-javascript.com/&sa=D&ust=1463755268762000&usg=AFQjCNFDsWg1nnopHG9iINwEBE5QFWFkMQ)
* Find files d3.zip, 4.3 d3\_chord\_online.html and 4.4 d3\_chord\_offline.html\(they’re all in the Notebooks directory\) - put them into the same directory, somewhere you’ll easily be able to find in the terminal window.



## Session: Cleaning and Exploring Data {#h.g7p2u1ckbdw5}

You need to:

* Install OpenRefine

### 1. Install OpenRefine {#h.m479ooo106bk}

DO THIS: Go to[http://openrefine.org/download.html](https://www.google.com/url?q=http://openrefine.org/download.html&sa=D&ust=1463755268765000&usg=AFQjCNHv5PLTYxh0Jn0cQUGRQD092e166A); click on the download for your PC type \(Mac, Windows, Linux\)

MAC:brew cask install google-refine

## Session: Predicting values from data {#h.vmayxj22dssn}

No installs needed

## Session: Handling text data {#h.wj0t53kxug9a}

No installs needed

## Session: Handling geospatial data {#h.s3j9hgwl06d3}

You need to:

* Get Cartodb account
* Install GDAL, QGIS
* install the Fiona and Shapely python libraries

### 1. Get Cartodb and Qgis {#h.pv6g993gwopi}

DO THIS: go to[https://cartodb.com/](https://www.google.com/url?q=https://cartodb.com/&sa=D&ust=1463755268769000&usg=AFQjCNHfPa0tZmFeISYfXCNvB79bLP7cNg), click "sign up"

DO THIS: IF YOU'RE ON WINDOWS: Go to[http://www.qgis.org](https://www.google.com/url?q=http://www.qgis.org/&sa=D&ust=1463755268769000&usg=AFQjCNF1gwf3F-o1amrC985EyoDUZ86s3A); click “download now”

DO THIS: IF YOU'RE ON A MAC:

* Step 1: Go to
  [http://www.kyngchaos.com/software/frameworks\#gdal\_complete](https://www.google.com/url?q=http://www.kyngchaos.com/software/frameworks%23gdal_complete&sa=D&ust=1463755268770000&usg=AFQjCNGmR0uyL_eYodlooXiKr9ufZaB_6w)
  ; Download the first option "GDAL 1.11 Complete Package" and follow the installation instructions.
* Step 2: Go to
  [http://www.kyngchaos.com/software/python](https://www.google.com/url?q=http://www.kyngchaos.com/software/python&sa=D&ust=1463755268771000&usg=AFQjCNGAfRBvYNU5Re5eicRM2zf_1UobOg)
  ; Choose "matplotlib 1.3.1-2" from the list of Python modules. Download and follow the installation instructions.
* Step 3: Go to
  [http://www.kyngchaos.com/software/qgis](https://www.google.com/url?q=http://www.kyngchaos.com/software/qgis&sa=D&ust=1463755268772000&usg=AFQjCNGl2GDcWxKFIFk4NrJWQasZDD_RDA)
  ; Click on "QGIS 2.6.1-2”; Download and install , and QGIS should be working!

### 2. Install Python GIS libraries {#h.j4uyajxcsr6m}

DO THIS: In the terminal window, type

* pip install fiona
* pip install shapely

If installing fiona fails because it cannot find the gdal.h file you need two export statements. Enter:

export CPLUS\_INCLUDE\_PATH=/Library/Frameworks/GDAL.framework/Versions/1.11/Headers

export C\_INCLUDE\_PATH=/Library/Frameworks/GDAL.framework/Versions/1.11/Headers

This assumes you installed the GDAL 1.11 Complete package listed above. After you enter these export statements in the Terminal, run thepip install fiona again.

## Session: Learning relationships from data {#h.9uyv6cxrccty}

No installs needed

## Session: Working with data science teams {#h.lweeilomicxs}

No installs needed

## Session: Enterprise data tools {#h.4qnr09yxwhic}

No installs needed

## Session: learning classes from data {#h.c1xuh7lqmk2l}

No installs needed

## Session: Handling big data {#h.7jvt439eid2r}

No installs needed

## Bonus: things you might want to play with {#h.1d8978jjbrf8}

No installs needed



  


