# Merge Intervals
We use this pattern to solve problems with overlapping intervals. 

Given two intervals, there will be 6 ways that they interact with eachother:

![[Pasted image 20220514220910.png]]

1. `a.start < b.start` and `a.end < b.end`.
2. `a.start < b.start` and `a.end > b.start`.
3. `a.start < b.start` and `a.end > b.end`.
4. `a.start > b.start` and `a.start < b.end`.
5. `a.start > b.start` and `a.end < b.end`.
6. `a.start > b.start` and `a.end > b.end`.

## Example
> Given a list of intervals, **merge all the overlapping intervals** to produce a list that has only mutually exclusive intervals.

In this problem, we need to find intervals that overlap. We can start by sorting the intervals by the first index to ensure the list is in order. Then, we will go through and check the 2 and 3 conditions above to see if intervals overlap. If they do, we will merge the intervals (i.e new interval = first, max(a.last, b.last)) and put them back into the list.

## Problems
### Insert Interval
> Given a list of non-overlapping intervals sorted by their start time, **insert a given interval at the correct position** and merge all necessary intervals to produce a list that has only mutually exclusive intervals.

We insert the interval based on where it falls in the list with its first index. Then, we go through the list and run the previous algorithm to merge the overlapping intervals into one, making the list mutually exclusive.