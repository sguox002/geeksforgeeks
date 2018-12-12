1. Find four elements that sum to a given value
find two sum and store in another array, reduced to 2sum

2. Save Ironman
ignore symbols, and only leave alphanum, then check if it is pal

3.How Many X's?
given a digit x, and a range a to b (exclusive), count the number of x
just make the a and b same length and then it is simple
for example if 2 can appear on hundred, we can have 2xx: it is 100+10+1

4. Check if array contains contiguous integers with duplicates allowed
just put them in set, and check one by one

5. Pairs with Positive Negative values
separate into positive and negative and to see if they match

6. Prime number of set bits
given range [a,b]. The prime number from 1 to 32 is very limited.
naive: 
build a map of primes
count each number's 1

7.Find k-th character in string
binary string of m
n operations: 0-01, 1-10
this is like a tree, and find the kth leaf node
every operation will double the length
can save some if we know which char generates it

8 Left Rotate Matrix K times
for matrix
AB
CD
rotate one: 
CA
DB
rotate 2 (up down, left right reverse)
DC
BA
rotate 3
BD
AC
rotate 4: restore
so just use k%4

9 Alien Dictionary
given k letters and n words in sorted order, return the letter order
for example
"baa", "abcd", "abca", "cab", "cad"
the first letter:
we got b->a->c
for abcd, abca, we got d->a
for cab, cad, we got b->d
this is a graph:
from source node to destination node, we need find a path containing all letters
if there is a cycle, it is against the rule.
using dfs

10. start element
star: greater than all its right side
superstar: greater than all its left and right side
return all the star and superstar members
get the lmax and rmax array from left to right, and right to left.

11. print all nodes without siblings
sibling: nodes share the same parent.
recursion, need to store first, and then sort

12. Construct Tree from Preorder Traversal
given the array and if each node is a leaf or not
preorder: node, left sub, right sub
this shall with constraints: 0 or 2 child node, for one node, there is more than a solution
using recursive. if it nonleaf,then recursive

13. Height of Spiral Tree
leaf nodes act as doubly linked list
hard to understand what it asks
now I understand, the leaf nodes are not normal leaf nodes.
Determine if it is a leaf we just check its left node (previous) and returns to its right (circular). Do not need to go around.

14. common subsequence
check if a and b shares a common subsequence
it is easy to check if they have a same char

15.Positive and negative elements
arrange array as positive+negative
too simple

16. Chocolate Station
get station[i]-station[i+1] when from i to i+1. He needs to buy chocolate to make it >0
initial he has 0 chocolates
return the min cost
Be sure to understand the problem correctly. From 0 to 1 we lost a[1] choco. That is the key.
using simple dp to represent the number of choco we have at the stage and accumulate what we buy

17. First and last occurrences of X
in sorted array with duplicates, find the lower and upper bound of x
binary search: using equal range stl

18. Sum of Lengths of Non-Overlapping SubArrays
Given an array of N elements, you are required to find the maximum sum of lengths of all non-overlapping subarrays with K as the maximum element in the subarray.
just iterate all elements and add the length including k. This effectively avoids overlap

19. Find the Highest number
first ascending order then descending order, find peak
using binary search. need check which side the mid point is and then shrink the searching range.

20. Similar expressions
only contains letters and + - and ()
using stack to remove all () for both string and to see if final is the same

final string: given each variable a + or - sign, check if the two map the same

21. Row with minimum number of 1's
row is sorted. using binary search

22. Total number of Strings
a,b,c a can be used any times, b can use max 1 time, c max 2 times
string length is n
all a: 1
all a with 1 b: b can at any position, n
this is easy to make mistake. using recursion is easier and also can apply to more complicated cases

23. Even and odd elements at even and odd positions
leetcode easy

24 Count triplets with sum smaller than X
sort and then use three pointers to count the triplets

25. knight steps
to target, min steps
BFS

26. Index of first 1 in a sorted array of 0’s and 1’s
binary search

27. leaves to dll
Given a Binary Tree, extract all leaves of it in a Doubly Linked List (DLL)





















