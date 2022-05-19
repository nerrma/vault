# Cyclic Sort
This pattern is used in problems involving arrays containing numbers in a given range.

## Example
> You are given an unsorted array containing numbers taken from the range 1 to ‘n’. The array can have duplicates, which means that some numbers will be missing. Find all the missing numbers.

To solve this problem, we can insert numbers into an array using their value as the index. So, 1 goes to index 0 and $n$ goes to index $n-1$. We can then check the empty values in the array to find which numbers are missing.

## Problems
### Cyclic Sort
>We are given an array containing ‘n’ objects. Each object, when created, was assigned a unique number from 1 to ‘n’ based on their creation sequence. This means that the object with sequence number ‘3’ was created just before the object with sequence number ‘4’.

> Write a function to sort the objects in-place on their creation sequence number in $O(n)$ and without any extra space. For simplicity, let’s assume we are passed an integer array containing only the sequence numbers, though each number is actually an object.

This is a simple application of the cyclic sort pattern. We can do an $O(n)$ sort by using the numbers as an index (i.e 1 goes to index 0, 5 goes to index 4) and we will have a sorted array at the end.

The rest of the problems are simply an application of this pattern and do not provide any more novel modifications of note.