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


## Source of Data
A csv, titled **Election_Results.csv** containing 3 columns with headers:
- ballot id
- county
- candidate
This should be stored in the **Resources** folder one level down from where the code is being executed

## Output
In addition to screen output, results are written to **Election_analysis.txt**, showing:
- total votes
- votes and percentages by candidate
- the overall winner
This is created in the **Analysis** folder one level down from where the code is being executed

## Structure
Creates a dictionary to store votes by candidate. 

Iterated row by row; 
- if the candidate picked in that row is not yet in the dictionary, the name is added
- candidate named in the row has there vote total incremented by 1

At the end, iterate through the dictionary entries
- read total votes per candidate
- calculate percentages of the total vote
- see who got the most

This information is then formatted, sent to the screen and the output file
