-	The crawler was speed up by 3% due to changes in the way the yaml file was loaded.
https://github.com/UTMediaCAT/Voyage/commit/c86d97d31e1f06b107a4ae5b6397717af8efceac

The profiler gave all stats per method (C profiler). Conclusion: the parser takes much longer than the parser.

The c profiler gives a python object that you can do with it anything you want, there might be an easier way to do it.

Q: Is there things newspaper does that is unnecessary for us? a configuration we can change?

A: The settings for newspaper have been configured already for our purposes (example: we dont download images into the crawler).  The remainder of the settings in Newspaper only fine tune small things.

-	Plan B crawler goes through 5000 links and gets 1 article

Controlled experiment – target a site that is interesting to the client and use crawler A & B to get stats of what each crawler gets on the same sample.  There is no condition to stop plan B from getting the same data on each site.  There is a page limit on plan B for each site so that it can move to the next site in a reasonable amount of time.

Pick 3 sites and set up a separate instance to test over a 3 day period.

Another solution is to cashe the crawlers state so it doesn’t spend time on pages it already has visited whenever the process is restarted.

The 5000 number included all types of files on the web and should only include html pages, right now that figure includes all resource types.

-	Other than that are we collecting a good set of data for the client. For the most part we have a good amount of tweets and articles for running over 2 months.

-	Next step for developers is to run the crawler for a long time on a focused scope (~3 referring sites) to understand the differences between Newspaper and Plan B.

**Next Meeting: Wednesday July 29 on Skype 5:30pm**

**Next Next Meeting: Thursday July 30 downtown 4:00pm**
