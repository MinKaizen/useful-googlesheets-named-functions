## Useful GoogleSheets Named Functions

## MATCHLAST

### Description

It's basically `MATCH`, but instead of matching the first ocurrence, it matches the LAST ocurrence. Useful when you you have transactional data and you want the most up-to-date value.

### Usage
Use it like you would an index/match statement. Let's say you have a table like this:
```
Username | Score
```
You could get the latest score by username like this:
```
=INDEX(B:B, MATCHLAST("minkaizen", A:A))
```

### Arguments
1. search_value
2. range

### Definition
```
=MATCH(2, 1/(range=search_value), 1)
```

## ArrayBetween

### Description
Given a starting cell and an end cell, returns the array of cells betwen those two points. For example:

### Usage
```
ARRAYBETWEEN(A1,A5)
```
This returns the range `A1:A5` (5 rows)
```
ARRAYBETWEEN(A1,B10)
```
This returns the range `A1:B10` (10 rows, 2 cols)

### Arguments
1. from
2. range

### Definition
```
=let(startRef,address(row(from),COLUMN(from)),endRef,address(row(to),COLUMN(to)),if(startRef=endRef,{indirect(startRef)},arrayformula(Indirect(startRef & ":" & endRef))))
```

