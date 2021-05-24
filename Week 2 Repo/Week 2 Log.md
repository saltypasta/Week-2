# Week 2 Log

## Excel & R

- What the heck is R
  - *RExcel is an addin for Microsoft Excel. It allows access to the statistics package R from within Excel. The main features are: Data transfer (matrices and data frames) between R and Excel in both directions. Running R code directly from Excel ranges.*
- Thanks wikipedia
- First step is to import csv file I downloaded from stats can. I unzipped it but it still isnt showing up. The tutorial says it might be i have an old version of excel and may need to turn on the Text Import Wizard
- Yup that was the problem
- Next step is to import the csv data we downloaded... There are two files.. maybe we should use both?
  - It only lets me import one at a time so Im going to use the one titled 98-400-X2016001_English_CSV_data 
- got a message saying the text wizard detected the data is Delimited. I dont know what that means but it did say in the meta data file that it was delimited so ill say yes
  - 'Delimited data is stored as two-dimensional arrays of data, where fields are separated by a delimiter. Any character may be used as a delimiter, but the most common delimiters are the comma, tab and colon. Comma Separated Values (CSV) files use a comma as the delimiter. Fields can be any length'  
  - Thanks google 
- Okay so after importing the data it looks like a hot mess
- Made a new sheet, went under data tab, clicked get data, and then used 'From file//from text/CSV' and it worked perfectly
  - Text wizard didnt work. I wonder if its because I dont have an old version of Excel 
  - Or I didnt use the right settings it prompted me with when i imported the Data 
  - Fricken Wizards man  
- Using the data to do a sum function. easy stuff
- Making a basic chart, I dont remember being able to hold ctrl to select my second piece of data... that would have saved me lots of time in the past
- Annnnd we are done the Excel portion! we will be going back to excel for pivot tables later
## The dreaded *R*
- Anaconda time!
- Holy moly this takes forever to load on my fiance's laptop
  - Missing *Leia* (My gaming desktop with an SSD) right about now... its too bad she isnt portable
- And we are in!
- Uh oh
  - First few chunks of code worked fine, but "x <- getURL("https://raw.githubusercontent.com/shawngraham/exercise/gh-pages/CND.csv", .opts = list(ssl.verifypeer = FALSE))" gave me an error message as follows
  - Error in function (type, msg, asError = TRUE)  :
  error:1407742E:SSL routines:SSL23_GET_SERVER_HELLO:tlsv1 alert protocol version
  - Thank god for discord and everyone talking through their work. Two other students have the same error and Prof posted new code that should work
  - So instead of:
    "x <- getURL("https://raw.githubusercontent.com/shawngraham/exercise/gh-pages/CND.csv", .opts = list(ssl.verifypeer = FALSE))" 
  - We now use:
    x <- "https://raw.githubusercontent.com/shawngraham/exercise/gh-pages/CND.csv"  
  - Followed by:
    documents <- read.csv(x)   
  - Boom, no longer a hot mess
- Graphs are dope
  - Immediately the power of these tools is obvious. being able to sort through large amounts of data and present it in meaningful contexts to answer or ask historical questions is awesome. In the same breath, I know why this has its limitations as well... Our collection methods and the way we choose to represent the data could just as easily be 
 misleading as it can be informative. *with great power comes great responsibility*
- I Saved my Rscript in a text file in week2 repo to be able to go back to where I was. I *should* be able to copy that and run it and replicate my work?

# Wget
- I have been warned not to download the internet
- lets not do that
- Using powershell, ran all steps up to:
  $ wget http://activehistory.ca/papers/
   -This looks like its doing stuff but I cant find any files in my directory... Unless im not looking in the right spot?
   -Once again discord saves the day! You need to add '.exe' to the end of wget in "wget -r -np -w 2 --limit-rate=20k http://activehistory.ca/papers/"
   -Correct command looks like:
   $ wget.exe -r -np -w 2 --limit-rate=20k http://activehistory.ca/papers/     
   - Okay soooo its still downloading... Im hoping I did not download the internet like I just said I wasnt going to
   - Stilllll going. I asked in the discord if anyone knows a way to find out how many files you are going to download before starting the command. the files are very small but my powershell is running forever and I am trying to progress with the tutorial.  
   - Well it stopped downloading as soon as I asked the discord but thats fine. I still would like to know if there is a way to get that information or if it is impossible by nature  
- moved urls.txt file to same directory as powershell is using since I got an Error
  - It helps a lot if you save the file after you put the urls in it 
- Ran the .py file to get the URLs no issue!
- Running the same command as before (wget.exe -r -np -w 2 --limit-rate=20k http://activehistory.ca/papers/) and im downloading war diaries! This is awesome!
- I discovered how we use the "urls.py" program in python to generate a sorted list of URLs that we can then download. I opened this text file in atom before running wget so I could see how many images I was about to download in advance. Not sure if there is a more efficient way to do this, or if you could actually know the file SIZE in advance aswell somehow but I thought it was worth mentioning in the discord in case someone knows another way.
