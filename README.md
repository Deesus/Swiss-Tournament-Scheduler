# Swiss-system Tournament Scheduler

#### version 0.86

### Schedule rank-based tournament matchups:
The **Swiss-system Scheduler** is a Python module that implements the [Swiss-system](https://en.wikipedia.org/wiki/Swiss-system_tournament) for **scheduling player pairing in each round in a game tournament**. The Swiss-system is non-elimination tournament format where all participants play multiple rounds of competition before the final rankings -- based on wins and opponent strength -- are determined. The module supports multiple simultaneous tournaments.

**N.b.** This is an old project; I've uploaded it for archiving purposes. However, it should still work perfectly fine.

### Quickstart:
1. Clone this repo, if you haven't already.
2. `cd` to the `/tournament` folder.
3. Setup the PostgreSQL database with the command, `psql -f tournament.sql`

### Usage:
Add players into database with the `register_player()` function which takes a single string argument.
```
register_player("Yuri")
```
Almost all of the other functions have the optional `tournament_id` argument, which specifies the tournament of which the match belonged. This allows the **Swiss-system Tournament Planner** to track, archive, and calculate the rankings and matchups of multiple tournaments concurrently. We can also have the same individual participate in multiple tournaments simultaneously.

Report and archive match results with the `report_match()` function. Insert the id's of the winner and loser of a match, respectively (with the optional `tournament_id` argument).
```
report_match(12,17)
```
Simply call the `swiss_pairings()` function, and the module will calculate the next pair of player matchups for a given tournament. Finally, `player_standings()` returns the current rankings/standings of the given tournament.

### What's included:
Inside the **Swiss-system Tournament Planner** directory, you'll find the following files:
```
Swiss Tournament Planner/
    ├──tournament.py
    ├──tournament.sql
    ├──tournament_test.sql
    └──README.md
```

### License:
MIT License.

