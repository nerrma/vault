# Two Pointers
Useful in problems with sorted arrays or linked lists to find a ceratin set of elements that fulfill constraints. The set of elements could be a pair, triplet or a subarray as in [[Sliding Window]]. 

## Example
> Given an array of sorted numbers and a target sum, find a pair in the array whose sum is equal to the given target.

A brute force approach would compare all pairs in the array with a $O(N^2)$ time complexity.

A hashmap would be $O(N)$ best case, though still $O(N^2)$ when taking the worst case complexity for retrieval.

As the array is sorted, we can use the two pointer approach. We check if the two pointers add up to the sum. We have one pointer at the start and one pointer at the end. If the sum if smaller than the target, we increment the smaller pointer.  If the sum if greater than the target, we decrement the larger pointer. This will also be $O(N)$ and will use less space than the hashmap.

## Problems
### Remove Duplicates
>Given an array of sorted numbers, **remove all duplicates** from it. You should **not use any extra space**; after removing the duplicates in-place return the new length of the array.

As the array is sorted we can use the two pointer method. Two pointers at the start with one ahead of the other. If the values of the two pointers are equal, increment the one higher to find the end of the duplicates. Once found, remove the duplicates between the two indices and continue. This is an $O(N)$ solution.

### Squaring A Sorted Array
>Given a sorted array, create a new array containing **squares of all the number of the input array** in the sorted order.

Input: [-2, -1, 0, 2, 3], Output: [0, 1, 4, 4, 9]

We can use the two pointer method to cut down on redundant calculation and sorting. Start one pointer at the beginning and one at the end. Calculate the squares of the values at the pointers. Insert the largest value of the pair into the sorted array and move this pointer towards the center (i.e increment lower pointer, decrement higher pointer).  

### Triplet Sum to Zero
>Given an array of unsorted numbers, find all **unique triplets in it that add up to zero**.

First, we can sort the array to make search easier ($O(N \log N)$). Then, for each number, we use the two pointer method to try and find a pair in the array which adds up to exactly the negative of that number. For example, if the current number if $X$, we look for $Y + Z = -X$ so that $X + Y +Z = 0$ to fulfil the problem statement. This whole process will therefore have time complexity $O(N^2)$.

### Triplet Sum Closest to Target
>Given an array of unsorted numbers and a target number, find a **triplet in the array whose sum is as close to the target number as possible**, return the sum of the triplet. If there are more than one such triplet, return the sum of the triplet with the smallest sum.

We can apply an approach similar to the previous problem, using every element as an *anchor* and doing a two-pointer search for a pair which adds to the target. We may not find it, though the pointers should stop at the values closest to the desired value. We then keep track of the sum closest to the target and update it if we encounter a sum which is closer.

### Triplets with Smaller Sum
>Given an array `arr` of unsorted numbers and a target sum, **count all triplets** in it such that **`arr[i] + arr[j] + arr[k] < target`** where `i`, `j`, and `k` are three different indices. Write a function to return the count of such triplets.

Similar approach to previous problem, just counting the pairs we find which are less than the target in our search.
