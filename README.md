# atp-tennis
Generating CSV data for ATP tennis matches

(Update: I just noticed that Jeff has updated his data on Feb 7th after about a year).

This relates to Jeff Sackmans' ATP data (tennis-atp-master).
Jeff has not updated his files for a year, since AO 2016. It seems that he will not be updating them, so I am updating as best as I can.

There are some issues with the generation of missing data:

- JS uses his own code for players, I have mapped ATP's existing codes to his, but what will we do with new players ?
  I am not sure why Jeff created his own code, instead of using ATP's.
- There are discrepancies between Jeff's data and ATP. I don't know which is wrong. I am going with ATP.
- `match_num`: Jeff does not use the ATP code for a match. ATP code starts numbering with final as 1, and semis as 2 and 3, and so forth. Jeff uses 300 for the final, and then decrements. In some cases, he starts with 127, not 300. I think he is using his own code, since there are no codes in the ATP data for a walkover. So we need a code to sort.
- Jeff's `tourney_id` also differs from ATP in several cases. I am going forward using ATP's `tourney_id`. I was about to convert to Jeff's ids but i notice that the ids are okay for 2015 and before. In 2016, he has padded some id's with a zero such as Chennai, and in some cases the tourney_id is replaced with M020 or M001. Since this anomaly has happened in 2016, I am not sure whether I can continue it, since I do not know what he had in mind for the events that were to follow. Why did he change in 2016?
 I am trying to follow Jeff's tourney_id's.
- tourney_level is "A" for 250's and 500's. There should be a way of distinguishing between these.
- I have not yet included Davis Cup data. It's not there on the ATP site, I'll have to look for it. It's not on my list of priorities.
- Going forward, I am not sure how long I will continue updating this. That is because the data format is not too helpful. For example, I cannot calculate how many aces a player has. All the match_stats are stored in a match in a format that does not allow this. I am not sure what the purpose of the existing format is. This data should be stored against player_id and match, so that we can total based on year, season, surface, event etc for a player, or event etc.
- i have added some data in my parsed files such as number of sets played, number of tiebreaks. This will not reflect in the generated CSV since that has to be updated in the existing database. They are in the TSV files along with player codes and match_code used by ATP.

I will prepare data for 2016 and 2017, but beyond that depends on whether others are interested, and how much work is involved. I have data for 2016 ready but this has to be checked.


Feedback appreciated.

Observations:
- Brisbane has a draw of 28 as per ATP, not 32 (JS's database has 32). In fact, it seems that all events with a draw of 28 are showing 32. There are only 28 matches.
- match_num is 301 minus ATP's match_num. So MS001 becomes 300. Final is always 300, SF 299 and 298. No, majors have the final as 126 or 226.
- Height. I don't know why height is mentioned here. Jeff's height varies from the ATP one, and often is missing. In some cases, it tallies with the wikipedia entry. I use the ATP height.
- Names: The ATP names contain hyphens, such as Tsonga and Yen Hsun. JS's names don't and some have a middle name too.
- Start dates often are one day off and in Olympics are several days off. This affects the age which is to ten decimals. Why is age in so many decimals ???
