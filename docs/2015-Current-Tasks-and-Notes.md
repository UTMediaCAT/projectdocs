# Open Issues in Github

https://github.com/UTMediaCAT/Voyage/issues

#Move server

## Dec 3
* Turns out that WARC'ing is going faster than we thought: approximately 800 URLs in 5 hours; 4 simultaneous processes take 1.7 GB Ram, with 2 processors. 
* 

## Nov 26

* After 1pm meeting to go through ideal backlink export format for priority queuing
* Priority queuing using the Google, in the form of "keyword site:"
* Team to Meet on tuesday for Diagrams and testing
* testing over summer - 1 instance to 1.5 instance per cpu core
* also in future parallel per site couple of nytimes still 1-1.5 per core
* Jai got his placement because of the work he did for UTMEDIACAT!

## Nov 19
* have documentation, diagrams ready for all processes
* test new database and see how much RAM/cpu space is required
* get email wording for permission to crawl sites
* cost few hundred
* set up meeting in mid December
may need more than 60gb
RAM depends on how many sites in parallel
swap space is slow if accessing all sites and accessing all memory
an instance for 3 sites is 4gb memory being used
will cost few hundred dollars with IITS

#Database:

## Dec 11:

3 site paused when out of space but resumed afterwards. 60gb on digital ocean most taken out by logs, text files to see error codes. logs not rotated. cron job to delete log searches, using 14gb for 3 sites for 2 weeks incl ram and swap space. move to db would be the same or more in terms of site timing
if a db, marginally more optimized but move to db may be a little bigger but not much more

William working on this, status is not ready to use, needs debug, check performance, check alternate ways to fix, 14gb
timeline on that is that it will happen after the break

## Dec 3:
* Met to try do the MySQL: couldn't easily transfer the SQLite database to MySQL, so in the end, it might be easiest to have the Bot Discovery (Plan B) use MySQL for its RAM database, and keep the result database in SQLite. This will help with testing to ensure stability. Try to do for next week.
* Still need to incorporate the saving of source URLs, and implement the changes to UI.

## Nov 26:
MySQL update: Not yet work on implementation

Entering them through web interface
Testing them solution: get all selectors from db from a given site, evaluate a given page for every selector in place. vs. paste in every time. Create account for vinnie, login and test ssh connect to db.

Alternate option: Django page instead to run and test selector

Source articles - Jai - in progress
now working for new results. but now have to go and do it retroactively - make a script to go and get the source sites now


## Nov 19:
* meeting yesterday for the database selection
* thought of how to optimize going with MySQL with Django implement
* Django can have multiple have dbs, keep existing SQL lite and implement new mysql database
* add the archiving of source articles that are found, and have this reflected in the interface - deferred


## Nov 5:
* add the archiving of source articles that are found, and have this reflected in the interface 

# Weekly sweeps
## Nov 26
* newspaper sweeps is fine - Alejandro to add still

## Nov 19
daily weekly sweeps is fine for newspaper
* need to add all the necessary referring sites - deferred for Alejandro to add

## Nov 5: 
* started without a hitch
* need to add all the necessary referring sites

# WARC

## Dec 3:
* For easy viewing, we thought we would put a PDF version of webpage as a link. However the Phantom JS process for the PDF is taking a long time. We will wait to see if Roger has a solution, and if not, perhaps we will look into adding a WARC viewer.

## Nov 12
* WARC'ing is stable, can do a maximum at 2 WARCs at a time, but this can be increased
* PDF-viewer: this is nearly ready, just need to have code merged
* there was only one bad WARC

## Nov 5
* WARC'ing is not done: there was a memory crash
* WARC: dynamic number of processes based on how much memory is available
* WARCs have been checked

# Crawler (Plan B) Test on NYT, CNN, BBC 

## Dec 11:

nytimes, bbc, 2 weeks only being restarted
finding unique ones still
nytimes 1 million
bbc 900 000
cnn 470 000
CNN the most hits so far likely because of transcripts

google for mentions keywords not for backlinks
ahrefs better you can filter it better, able to filter, they had some sort of ability to do so and then pay for those links
if you're using that need a program, using API charges more. API command not helpful


## Dec 3:
* New Terminology: Bot Discovery for the Plan B, and Newspaper Crawler is RSS Discovery
* test Bot Discovery with WARC'ing processes.
 
## Nov 26:
CSS selector update:
Made tool for testing CSS selectors. Current solution is doing it in the browser. Browser CSS selectors might not be the same implementation as the XML one - depends on which browser you use. Python script to use the xml stuff, same stuff that the crawler uses to test accurately. Needs SSH access to server needs access to get database to site. 


* display and keyword matched keyword - highlight keyword
* costly to do for every article taking too much time
* shows all text and highlights all matching keywords
* crash in 2 weeks but ran again and since then hasn't stopped
* anchor text is halfway there - the text of links

## Nov 19:
* crawler not run this week, will run next week
* implement to store the text as well for each article, naive implementation to show the text around the found keyword based on text and matched keyword. recreate in articles. not currently stored in database. full text stored so see surrounding text. takes 5-10 seconds to load text in "Matched Keywords" - this will be used for the comparison of text when it's separated out
* anchor text is still required - william and yuya getting the link

lots of cn.nytimes.com 


## Nov 12:
* no crash, but 2 processes are stuck, might be external
* Next Tuesday: Yuya, Jai, and William will meet to talk about database
* no other problems as of right now.
* we'll attempt to separate out the text of the article in order to make it available for comparison on re-crawls
* finding about 20 hits a day, mostly on NYT
* CSS selectors: 

## Nov 5:
* database/save state: not yet working; don't go with sql-lite; use MySQL or other
* we will increase server capacity to 40 gb & 4gb RAM, 
* We are targetting December to finish implementing the database, and getting ready to do a baseline crawl.

# Optimizing plan b crawler:

## Dec 11:
priority queuing: few hundreds can be found, doing the whole thing would be difficulty
limited results but many duplicates

## Priority Queuing (Oct 15):
* search google for all aliases and then queue those hits.
* problem: google doesn't search embedded links, would need a source code search for that, so Alejandro is going to write to google.
* looking at getting backlinks from a company.

## multi-threading on single site: 
* where one process is downloading/queuing and one process is analyzing metadata 
* leave until later, need to iron out bugs with crawler first.

## multi-threading for multiple sites: 
### Oct 15
* Implemented multi-threading
* Implemented log per site

### Oct 8
* William will implement newspaper code for analysis, and Yuya will test it; 
* William/Yuya will also implement a log per web domain per crawl (instead of all together)
* fixes that were implemented to crawler need to be implemented in the multi-thread crawler, needs to be done manually - William
* keep on eye on this: readability issue was implemented over the summer, and this makes the crawl faster, but that also leads to greater instability, the source of the errors we saw this week.

# CSS Selectors

## Dec 3
* Code for testing CSS selectors, but it needs to be incorporated into the UI.

## Nov 19
UI for CSS selectors on the site - for adding selectors. go to a site in referring sites and click on the site, can add css selectors at the bottom of the page
needs to be hooked up to the crawler
right now only hooked up to date modified and author
* will Alejandro want to add CSS selectors to the old database sites as well? will he use the old database?

## Nov 12
* code is implemented to find CSS selectors as part of Newspaper, but we need UI on the site, so that a user can go in and plug in CSS selectors based on domain
* 

## Nov 5
* need some examples from Vinnie of CSS Selectors that need regular expression trouble shooting

