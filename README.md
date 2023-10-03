# bjj_network

BJJ Athletes tend to compete against each other quite a bit. 
Would network analysis be a useful tool for "ranking" or comparing athletes in similar weight classes against each other?
My hypothesis going into this would be that some key clusters would appear, likely by weight class and sex, with a visual difference between someone who has competed against everyone in a a cluster compared to someone who has beaten everyone in a cluster.

For this project I used beautiful soup to scrape athlete names, links, birthdays, record, and match history from flo grappling. I created a database to store this information with two tables, one for the name, link, birthday, and record, and another for all the matches I was able to scrape. I was able to create several functions to execute these steps and eventually I was able to create and clean dataset of over 38,000 matches and 1400 athletes. This was all done in bjj.ipynb.

I then made a new notebook where I loaded in this sql data and cleaned it, parsing out pieces of text that I needed to standardize the id's as well as create a total match column. I first experimented with making a network on some fabricated data, but then I got to work using my data. As can be expected, based on the sheer volume of my data it was difficult to interpret a network in 2D space. From here I did a few things, I made a subset of data for athletes that had at least 20 matches, as well as only included matches from the last 5 years. I used the NetworkX package to create my network and eventually wanted to use the Pyvis package, which I was able to do as is seen in the html files attached. These are very large but will run if given time. 

Next, I've made functions to analyze a given athletes first and second degree connections, this has resulted in a much more manageable graphic.

I also performed a more traditional analysis of "Favorite Submission" in general, but also on win percentage. The most common submissions are Choke From the Back, Armbar, and Rear Naked Choke (I allowed Choke From the Back to be its own entity). Though it should be noted that the majority of matches do not end in submission, and the most common method of winning a match is by Deicsion or Points, to me this stresses the importance of takedowns and cardio. 

Looking closer, I analyzed the matches for all the athletes in my sample over the last 5 years, coming up with a favorite submission and a recent win percentage.
I added this information to the database as well then began to do exploratory data analysis and statistical tests. Win Percentage was not normally distributed, so I used the kruskal wallis test to first to compare medians, then used conover's test for paired posthoc analysis. 

Overall this analysis has showed that having some favorite submissions are statistically better than not having a favorite submission, though this should be interpreted carefully. This sample is heavily imbalanced, for instance there is only one individual athlete who's favorite submission is the Anaconda Choke, but they have a win percentage near 80%, so the coefficient in our regression is very high. 

In terms of recommendations, from this analysis getting to the back is likely a good strategy as both Choke From the Back and Rear Naked Choke are statistically significant with a 20% difference in win percentage. Removing the submissions with only one athlete, I would also recommend the Armbar, Americana, and Straight Ankle Lock.

For me, time to drill armbars instead of throwing my leg over and eventually fighting from turtle.
