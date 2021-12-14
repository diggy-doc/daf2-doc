# Advanced Filter by formula
DAF2 provides a very flexible way of filtering neighbours: by formula and by gifts received. In this page, let's 
focus on by formula
### What are formulas
One formula is one or more conditions linked by logical operations (And, Or) and one condition is a field has/does 
not have a certain value. The fields include
- blocks: the number of uncleared slots in the camp, 0 means the camp is fully cleared
- level: the neighbour's level
- region: the neighbour's region, 1 for Egypt, 2 for Scandinavia, and so on until 7 for Terra
- wmtime: the windmill expire time

### Predefined filters
There is show dropdown options, actually most of them are predefined filters.
1. In custom list: list = 1
2. Not in custom list: list = 0
3. With blocks to clear: blocks > 0
4. Blocks state unknown: isnan(blocks)   blocks is not a number
5. With expired windmills: wmtime < now  windmill expire time is earlier than now, i.e. already expired
6. No gifts in X days (X can be changed by the next dropdown menu): lastgift < (now - giftdays * day)

### Other useful filters
1. camp cleared but still in the stone list or vice versa: (blocks > 0) <> (list = 1)
2. the neighbours visited today: visit >= today
3. player at certain level, e.g. more than 1000: level > 1000
4. neighbours with unknown camp or previously not cleared, useful while maintaining stone list but the friend list 
   is long: (blocks > 0 and visit < today) or isnan(blocks)

