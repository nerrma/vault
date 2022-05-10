# Sliding Window
Useful mainly for problems relating to contiguous subarrays. The idea is to define a *sliding window* which captures a certain number of elements and can be moved around the array to hold related data.

## Example
> Calculate the sum of all subarrays of size $K$.

The brute force approach here would find and recalculate the sums of all subarrays in the array. This means going through every element and calculating the sum of it and the next $K$ elements. This would therefore be $O(N*K)$ complexity.

The smart approach here is to define a *sliding window* of size $K$ and move it along the array, re-using the previous sum and subtracting the element leaving and adding the element entering the window. We have now improved the algorithm to $O(N)$.


## Problems
Increasing in difficulty.

### Maximum Subarray Sum of Size $K$
Simple application of the sliding window.

Calculate the sum for the first window of size $K$, then slide a $K$-size window across the array, subtracting the element leaving from the sum and adding the element entering. Simple `max` operation between interations to get the maximum.

### Smallest Subarray With Sum $\geq S$
Start at the first element and slide until we get a subarray with sum $\geq S$, store this as our minimum $m$. Slide the window over by one (subtracting previous and adding new element $e$). If $sum \geq S$, reduce the size of the window by 1 (removing the first element) and update $m$. Move along all elements until minimum is found. 


### Longest Substring With $K$ Distinct Characters
Starting at the first element, keep a simple map of letters (could be a bitmap) and increment the size of the window if the new letter does not exceed the $K$ distinct characters rule. If it does, move the sliding window to the next index and reduce the count for the letter being removed.

### Fruits into Basket
> Given an array of characters where each character represents a fruit tree, you are given **two baskets** and your goal is to put **maximum number of fruits in each basket**. The only restriction is that **each basket can have only one type of fruit**.
> You can start with any tree, but once you have started you can’t skip a tree. You will pick one fruit from each tree until you cannot, i.e., you will stop when you have to pick from a third fruit type.

This can be reinterpreted as finding the longest substring with 2 distinct characters.

### No-Repeat Substring
Start from the first index and extend the sliding window. Keep a hashmap for the current window, updating it when moving (removing old count and adding new count). If the next character to be added to the window has a conflict with the current window, move the window one index (i.e remove the first entry).

### Longest Substring with Same Letters after Replacement
> Given a string with lowercase letters only, if you are allowed to **replace no more than $k$ letters** with any letter, find the **length of the longest substring having the same letters** after replacement.

Start a sliding window from the first index, keeping track of the current number of letters to replace and a map of the current letters. Ensure the count of one letter is at least $n-k$. If the number of letters to replace is greater than $k$, move the window over one.