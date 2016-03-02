# Updates have moved

https://trello.com/b/Y4g02YiL

# Open Issues in Github
https://github.com/UTMediaCAT/Voyage/issues

# IITS Server Move
* clear out VMs on Digital Ocean--Roger will check with Jai & Yuya
* decided on VM type and size
* 

# Optimization
* Roger is working on WARC and Crawl processes that take up so much memory, and can cause crashes

# UI & Public Portal:
* Roger will check with Jai about implementing Source/Referring split for data, and ensure that we are WARCing source URLs
* adding a language column to the database
* Jai will do the "alias" for the UI
* We have converted "weekly sweeps" into "main", and given it a password (see our channel).
* We are going to go with a clean, simple "Bootstrap" modern business portal
* For the portal, we will use "generic" tags for the statistics for now.

# Database
* William started it, need to do speed tests, and what happens when visit queues get large. Issue for how Django issues queries. Speed test will start Jan 6, and take 2-3 weeks.
* Yuya can help migrate the database to Django.
* Jan 13: William started test with full log, and on a few websites, with paging-version, to discover what procedures, and then will get the logs to test an instance with paging versus an instance with the database.
* one issue: al-Jazeera using much more RAM than NYtimes, crawl is much slower. Al-Jazeera is the problem we hope that database can solve. 
* Jan 27: database not working well. Paging was able to do 2 weeks of searches in bw 160-350 seconds, 139,000,000 operations, while MySQL did not deal with this well, doing only 1,000,000 in several hours. William will consult with other team members over dev channel of Slack. One possible solution is to "do queries ourselves" rather than rely on Django (too black boxy). One week is a possible for implementing this, asssuming everyone agrees that this is a good way to go. 

#Github issues
* did we resolve duplicates, #43 & 31? if not, how long? Yuya is looking at duplication.
* Dec 13: Vinnie is finding a lot of duplicates.
* going over Github issues, and prioritize them; make product roadmap with necessary features and deadlines
* get data sets from ahRefs, Factiva, Proquest (and mark these datasets, so that can query them specifically in future)
* make timeline for staged ingesting
* make good documentation

#CSS Selectors
* issue with domains having more than one set of CSS selector, so add as much as possible
* blacklist the mobile site? 