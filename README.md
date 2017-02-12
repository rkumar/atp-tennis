# atp-tennis
generating CSV data tennis ATP matches

This relates to Jeff Sackmans' ATP data (tennis-atp-master).
Jeff has not updated his files for a year, since AO 2016. It seems that he will not be updating them, so I am updating as best as I can.

There are some issues with the generation of missing data:

- JS uses his own code for players, I have mapped ATP's existing codes to his, but what will we do with new players ?
  I am not sure why Jeff created his own code, instead of using ATP's.
- There are discrepancies between Jeff's data and ATP. I don't know which is wrong. I am going with ATP.
- `match_num`: Jeff does not use the ATP code for a match. ATP code starts numbering with final as 1, and semis as 2 and 3, and so forth. Jeff ends with the final, so the number could be anything. I am not following Jeff's numbering, I am using ATP match numbers.
- Jeff's `tourney_id` also differs from ATP in 2 cases at least. I am going forward using ATP's `tourney_id.`
- I have not yet included Davis Cup data. It's not there on the ATP site, I'll have to look for it. It's not on my list of priorities.
- Going forward, I am not sure how long I will continue updating this. That is because the data format is not too helpful. For example, I cannot calculate how many aces a player has. All the match_stats are stored in a match in a format that does not allow this. I am not sure what the purpose of the existing format is. This data should be stored against player_id and match, so that we can total based on year, season, surface, event etc for a player, or event etc.
- i have added some data in my parsed files such as number of sets player, number of tiebreaks. This will not reflect in the generated CSV since that has to be updated in the existing database.

I will prepare data for 2016 and 2017, but beyond that depends on whether others are interested, and how much work is involved. I have data for 2016 ready but this has to be checked.

Feedback appreciated.
