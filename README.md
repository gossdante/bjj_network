# bjj_network

BJJ Athletes tend to compete against each other quite a bit. 
Would network analysis be a useful tool for "ranking" or comparing athletes in similar weight classes against each other? 



Database Considerations
There should be multiple tables. The first would contain the name, ID, and (potentially) record for each athlete. The second would contain the match details. The primary key would likely be the ID of the athlete the data was scraped from, which would lead to a duplication. This will be a one to many relationship, where each athlete appears once in table 1, but any number of times in table 2.

Immediate next steps:
Turn the code that gets all matches for a given athlete id into a function.
Run through each athlete id and create a master df.
Check ID's are consistent between both df's (will need to remove text in table 1).
