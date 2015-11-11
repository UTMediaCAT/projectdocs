# Friday Meeting

Eldiflor can not continue working as a tester but Kim may pick up from where he left off on some of the documentation

Twitter explorer just started running yesterday that is why there was no data for tweets.

Alejandro likes the metrics columns on the scope.

Q. How to know when to use plan A or B crawler?  
A. Some documentation in the user interface could be given however we eventually plan to not give the choice to the user and implement internal logic to determine what crawler to use

Issue: Plan B crawler needs more work to work faster
Method to make it faster:
- multi-threading
- potentially prioritize pages that will contain links to 

We could also optimize newspaper because it is taking 100% of cpu on mathlab. At least with newspaper issue is not as big of a deal since it finds the right articles immediately by looking at the RSS

Issue: Author detection is poor 
Potential Solution: Extend newspaper with Stanford NLP
Potential Solution: Human intervention to improve detection of elements in articles.  A possible feature that could be good is to implement rules for each referring site that could hone in on elements like author.  To do this the user would have to enter a CSS Selector to identify the pattern for authors on a specific site.

Request: A page for showing the status of the current crawling process. 

**Next meeting Friday 10:30am**