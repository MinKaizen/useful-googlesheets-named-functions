## Useful GoogleSheets Named Functions

## MATCHLAST

### Description

It's basically `MATCH`, but instead of matching the first ocurrence, it matches the LAST ocurrence. Useful when you you have transactional data and you want the most up-to-date value.

## Arguments
1. search_value
2. range

## Definition
```
=MATCH(2, 1/(range=search_value), 1)
```

## Usage
Use it like you would an index/match statement. Let's say you have a table like this:
```
Username | Score
```

You could get the latest score by username like this:

```
=INDEX(B:B, MATCHLAST("minkaizen", A:A))
```

