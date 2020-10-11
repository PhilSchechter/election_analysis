# election_analysis
data analytics course module 3
PyPoll_challenge.py
written in Python 3.7

## Purpose of audit
This project is to provide automatic, traceable results based on the raw election returns
This analysis can be used to verify results tabulated manually, or through other means,
such as an Excel pivot table.

As little as possible was hardcoded; for example, the candidate names and
counties were read in from the input file, not entered directly into the code

## Election Results
[Election Results](Analysis/election_analysis.PNG)

Diana DeGette won, and won big, with 74% of the vote.

In some more detail:
- 369,711 ballots were cast
- Diana took about 273 thousand, or 74
- Charles Caser Stockham had 85 thousand votes, or 23%
- Raymon Anthony Doane also ran, with 12 thouand vots, or 3%

Looking at votes cast by county:
- Denver had the lions share, at 306 thousand (83%)
- Jefferson was next at 40 thousand (11%)
- Arpahoe had 24 thousand votes cast, or 7%

## Summary of the process, suggestions for enhacement

### Source of Data
A csv, titled **Election_Results.csv** containing 3 columns with headers:
- ballot id
- county
- candidate
This should be stored in the **Resources** folder one level down from where the code is being executed

### Output
In addition to screen output, results are written to **Election_analysis.txt**, showing:
- total votes
- votes and percentages by candidate
- the overall winner
This is created in the **Analysis** folder one level down from where the code is being executed

### Structure
Creates a dictionary to store votes by candidate. 

Iterated row by row; 
- if the candidate picked in that row is not yet in the dictionary, the name is added
- candidate named in the row has there vote total incremented by 1

At the end, iterate through the dictionary entries
- read total votes per candidate
- calculate percentages of the total vote
- see who got the most

This information is then formatted, sent to the screen and the output file

### Validation
The program output was compared to a pivot table based on the same data

[Pivot Results](Analysis/Pivot_Validation.PNG)

confirmed:
- total number of votes matched
- total of votes per candidates matched
- total votes by county matched

The pivot process was quicker but more manual - would rather have a program with less human intervention
going forward, but the Pivot makes a good quick check.

### Possiblities for enhancement
Which minor modification, the program could show totals by candidate at the county level, which could 
help in any analysis of the results, or give targets for a more limited manual audit - e.g. if 
the results of any particular county look odd, that could trigger a manual recount. Technically, this 
could be achieved by using the disctionaries set up for total votes by county, and replicing the total count
with an inner dictionary tracking counts by candidate within the county

Furthermore, of the raw data is made available, this analyis could be applied to smaller areas - 
e.g. towships, polling places. If these smaller areas map smoothly into the counties (e.g. towns), could
use the same structure, just substituting towns for counties, and then adding up all the towns in a
county to get back to county level results if desired. Alternatively, may be easier to have seperate dictionaries
for town and county, not have to worry about adding everything back together at the end.
