# Merge Intervals
We use this pattern to solve problems with overlapping intervals. 

Given two intervals, there will be 6 ways that they interact with eachother:

![[Pasted image 20220514220910.png]]

1. `a.start < b.start` and `a.end < b.end` and `a.end < b.start` and `a.start < b.end`.
2. `a.start <= b.start` and `a.end >= b.start`.
3. `a.start <= b.start` and `a.end >= b.end`.
4. `a.start >= b.start` and `a.start <= b.end`.
5. `a.start >= b.start` and `a.end <= b.end`.
6. `a.start > b.start` and `a.end > b.end` and `a.end > b.start` and `a.start > b.end`.

## Example
> Given a list of intervals, **merge all the overlapping intervals** to produce a list that has only mutually exclusive intervals.

In this problem, we need to find intervals that overlap. We can start by sorting the intervals by the first index to ensure the list is in order. Then, we will go through and check the 2 and 3 conditions above to see if intervals overlap. If they do, we will merge the intervals (i.e new interval = first, max(a.last, b.last)) and put them back into the list.

## Problems
### Insert Interval
> Given a list of non-overlapping intervals sorted by their start time, **insert a given interval at the correct position** and merge all necessary intervals to produce a list that has only mutually exclusive intervals.

We insert the interval based on where it falls in the list with its first index. Then, we go through the list and run the previous algorithm to merge the overlapping intervals into one, making the list mutually exclusive.

### Intervals Intersection
> Given two lists of intervals, find the **intersection of these two lists**. Each list consists of **disjoint intervals sorted on their start time**.

We check the 2, 3, 4 and 5 conditions across both arrays. We can do this by comparing pairs from A to B, and terminating the loop when we find that none of the conditions are satisfied (i.e we don't have overlap).

In the 2 case, we take the interval `(a.end, b.start)`.
In the 3 case, we take the `b` as the interval.
In the 4 case, we take the interval `(a.start, b.end)`.
In the 5 case, we take `a`.

We can reduce this to `start = max(a.start, b.start), end = min(a.end, b.end)`.

We append these intervals to the result array and return.

### Conflicting Appointments
> Given an array of intervals representing ‘N’ appointments, find out if a person can **attend all the appointments**.

Simple check of overlaps using above conditions. We can first sort the array based on the first index, using the second index as a tiebreak. Next, we iterate through the array and check if neighbours overlap and return **true** if they do.