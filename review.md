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

28. Stickler Thief
same as house robber, dp 

29. Twice counter
count those words appearing twice
using hashmap or set

30. Second most repeated string in a sequence
hashmap. only need the most and second most

31. Check if Tree is Isomorphic
Two trees are called isomorphic if one of them can be obtained from other by a series of flips, i.e. by swapping left and right children of a number of nodes.
using recursive approach. See leetcode 951
compare left-left, right-right or left-right, right-left

32. Vertical sum
binary tree accumulate the sum
using level as key build a hashmap

33.Check set bits
all is set or not,
too simple, note the first 0 does not count
1, 11,111,1111,11111,
2^i-1

34. Number of Groups
choose 2 or 3 elements from the array and make the sum divisible by 3.
mod all number by 3 and get 0, 1,2
0 can combine with one 1 one 2 to form a 3 element
1 and 2 can be combined with 1 pair
for example: 1 5 7 2 9 14 after %3 it becomes 1,2,1,2,0,2, we have two 1s and 3 2s. 
The two element groups: 2x3=6
three 2 added: 1
0 with 1 and 2: 2*3=6
total=13

35. Rotten Oranges
rotten orange will rotten its surrounding oranges. the min time to rot all 
BFS

36.Find Pair Given Difference
Given an unsorted array Arr[] and a number N. You need to write a program to find if there exists a pair of elements in the array whose difference is N.
sort it and using hash to find a+N

37.Modify Linked List-1
Given a singly linked list containing n nodes. Modify the value of first half nodes such that 1st node’s new value is equal to the last node’s value minus first node’s current value, 2nd node’s new value is equal to the second last node’s value minus 2nd node’s current value, likewise for first half nodes. If n is odd then the value of the middle node remains unchanged.
use two pointer, one pointer at the head, one pointer at the second half.

38. Leftmost and rightmost nodes of binary tree
Given a Binary Tree, Print the corner nodes at each level. The node at the leftmost and the node at the rightmost.
Print the corner nodes ( nodes at the leftmost and nodes at the rightmost) at each level.
level to level traversal.

39. Count the elements
Given two arrays A and B. Given Q queries each having a positive integer i denoting an index of the array A. For each query, your task is to find all the elements less than or equal to Ai in the array B.
sort B and uses lower_bound

40.Top k numbers in a stream
Given N numbers in an array. Your task is to keep at-most K numbers at the top (According to their frequency).  We basically need to print top k numbers when input stream has included k distinct elements, else need to print all distinct elements sorted by frequency.
key: stream, sorted first using frequency and then using value.
Priority-queue is not convenient to update

Iterate through the array which contains stream of numbers.
To keep track of top k elements, make a top vector of size k+1.
For every element in the stream increase its frequency and store it in the last position of top vector. We can use hashing for efficiently fetching frequency of an element and increasing it.
Now find the position of element in top vector and iterate from that position to zero. For finding position we can make use of the find() function in C++ STL, it returns an iterator pointing to element if found in the vector.
And make that list of k+1 numbers sorted according to frequency and their value.
Print top k elements form top vector.
Repeat the above steps for every element in the stream.
a set of pair with own compare function will be good enough. searching is still a hard one.
we need add another data structure to support this. a hashmap and a vector. 
when a number is added, update the vector

41. Sum equals to Sum
Given an array A of distinct integers. The task is to find if there are two pairs (a, b) and (c, d) such that a+b = c+d, and elements of array are distinct. Array length is up to 1e5
since number is distinct, one number adds other will not produce same result.
just use naive solution would be fine

42. Group Anagrams Together
Given an array of words, print the count of all anagrams together in sorted order (increasing order of counts).
For example, if the given array is {“cat”, “dog”, “tac”, “god”, “act”}, then grouped anagrams are “(dog, god) (cat, tac, act)”. So the output will be 2 3.
anagrams are same letters, just sort each word and put in sets

43. K-Sum Paths
A binary tree and a number k are given. Print the count of every path in the tree with sum of the nodes in the path as k.
Note: path can start and stop at any node
always think recursion first.
1. check the number of path with root
2. check the number of path with left
3. check the number of path with right

Similar to dfs
add the node into path, check left subtree, check right substree
check the path exist k sum? This is a star problem, worth to study.
```cpp
int helper(Node* root, vector<int>& path,int k)
{
    if(!root) return 0;
    path.push_back(root->data);
    int ans=0;
    ans+=helper(root->left,path,k);
    ans+=helper(root->right,path,k);
    int sum=0;
    for(int j=path.size()-1;j>=0;j--)
    {
        sum+=path[j];
        if(sum==k) ans++;
    }
    path.pop_back();
    return ans;
}
```
44. Counting elements in two arrays
Given two unsorted arrays arr1[] and arr2[]. They may contain duplicates. For each element in arr1[] count elements less than or equal to it in array arr2[].
since we need keep arr1's order, there is two ways:
1. sort both array, but arr1 needs keep its original index, and then merge sort, and we get the ans
2. sort arr2, and iterate arr1 using lower_bound

45. Linked List that is Sorted Alternatingly
one way, put it into a vector and sort then change the node value

46. Uncommon characters
simple, count each char's occurence in each string

47. Maximum sum Rectangle
this is a conventional algorithm on submatrix. 

48. Game with String
Given a string of lowercase alphabets and a number k, the task is to print the minimum value of the string after removal of ‘k’ characters. The value of a string is defined as the sum of squares of the count of each distinct character.
apparently n^2-(n-1)^2=2n+1 so n is larger the difference is larger. 

49. Extract Maximum
You have been given an alphanumeric string S, extract maximum numeric value from that string. Alphabets will only be in lower case.

50. Root to Leaf Paths
```cpp
void get_path(Node* root,vector<int> path,vector<vector<int>>& res)
{
    if(!root) return;
    path.push_back(root->data);
    if(!root->left && !root->right) //a leaf node
    {
        res.push_back(path);
        return;
    }
    get_path(root->left,path,res);
    get_path(root->right,path,res);
    path.pop_back();
}
```

51. Fixing Two nodes of a BST
Two of the nodes of a Binary Search Tree (BST) are swapped. Fix (or correct) the BST.

inorder traversal got the sorted array. find the two nodes and swap.
1. not ajacent in inorder traversal, two conflicts
2. adjacent in inorder traversal, one flicts

we don't need to store all the numbers but only need to store the conflicts.

We will maintain three pointers, first, middle and last. When we find the first point where current node value is smaller than previous node value, we update the first with the previous node & middle with the current node. When we find the second point where current node value is smaller than previous node value, we update the last with the current node. In case #2, we will never find the second point. So, last pointer will not be updated. After processing, if the last node value is null, then two swapped nodes of BST are adjacent.


52. Find a pair with given target in BST
traversal and put them into hashmap.

53. AVL Tree Deletion
not familiar, need revisit

54.Huffman Encoding
not familiar, need revisit

55. Polynomial Addition
add the coeff with the same power, we can iterate the linked list and store the information in hashmap

56. Smallest distinct window
the window contains all the letters in the string
we don't care the number of each letter
We basically maintain a window of characters. Whenever the window contains all characters of given string, we shrink the window from left side to remove extra characters and then compare its length with smallest window fount so far.

57. Water Overflow
pascal triangle. dp, also appear in leetcode 799. Champagne Tower
split the remaining to its left and right.
dp: dp[i,j] represents the water for ith row, jth cup
if dp[i,j]>1 then dp[i+1,j]=dp[i+1,j+1]=(dp[i,j]-1)/2, and dp[i,j]=1
Note: 1. we need calculate more than 1 layer since the water will pour out when it is more than 1 or just set it 1 when it is >1


```cpp
double getwater(int k,int ii,int jj)
{
    vector<vector<double>> dp(ii+2,vector<double>(ii+1));
    dp[1][0]=k;
    for(int i=1;i<=ii;i++)
    {
        for(int j=0;j<i;j++) //has the same number as layer
        {
            if(dp[i][j]>1)
            {
                dp[i+1][j]+=(dp[i][j]-1)/2;
                dp[i+1][j+1]+=(dp[i][j]-1)/2;
                dp[i][j]=1;
            }
        }
    }
    return dp[ii][jj-1];
}
```

58. k-th smallest element in BST
inorder traversal. It may fully traverse
```cpp
void helper(Node* root,int &k,int& ans)
{
    if(!root || k<1) return;
    helper(root->left,k,ans);
    k--;
    if(k==0) {ans=root->data;return;}
    helper(root->right,k,ans);
}
```
Be sure to use reference call. use count++ may be easier

59.stepping number
A number is called stepping number if all adjacent digits have an absolute difference of 1, e.g. '321' is a Stepping Number while 421 is not. Given two integers n and m, find the count of all the stepping numbers in range [n, m].

for 1 digit: 0 to 9 are all ok: 10x1
for 2 digit: 12,23,34,45,56,67,78,89 (all x2) plus 10: 8*2+1
for 3 digits: 123,234,345,456,567,678,789 (all x2) + 210: 7*2+1
for 4 digits: 1234,2345,3456,4567,5678,6789 (all x2) +3210: 6*2+1
...
for 9 digits: 123456789 (x2) plus 876543210
there is no more for more than 9 digits
total number: 10+8*2+1+7*2+1+6*2+1+5*2+1+4*2+1+3*2+1+2*2+1+(1*2+1)
method1: generate all these numbers and sort. binary search is easy
method2: brutal force checking one by one
0123456789
123456789
23456789
3456789
456789
56789
6789
789
89
9

another approach using graph:
for example: 5
5->56 (5+1)
5->54 (5-1) by appending a digit
pay attention to the 0 and 9 at the end
0: no digit can be added
1->12, 1->10
2->23, 2->21

60. Top View of Binary Tree
naive: layer by layer: if next layer is smaller, it is visible, otherwise not
We can from left to right assign a x number to it. left is always 2n and right is always 2n+1 using full BST

61. Count subsequences of type a^i b^j c^k
Given a string s, the task is to count number of subsequences of the form aibjck, where i >= 1, j >=1 and k >= 1.
Note: Two subsequences are considered different if the set of array indexes picked for the 2 subsequences are different

We traverse given string. For every character encounter, we do following:

1) Initialize counts of different subsequences caused by different combination of ‘a’. Let this count be aCount.

2) Initialize counts of different subsequences caused by different combination of ‘b’. Let this count be bCount.

3) Initialize counts of different subsequences caused by different combination of ‘c’. Let this count be cCount.

4) Traverse all characters of given string. Do following for current character s[i]
    If current character is ‘a’, then there are following possibilities :
    a) Current character begins a new subsequence.
    b) Current character is part of aCount subsequences.
    c) Current character is not part of aCount subsequences.
    Therefore we do aCount = (1 + 2 * aCount);

    If current character is ‘b’, then there are following possibilities :
    a) Current character begins a new subsequence of b’s with aCount subsequences.
    b) Current character is part of bCount subsequences.
    c) Current character is not part of bCount subsequences.
    Therefore we do bCount = (aCount + 2 * bCount);

    If current character is ‘c’, then there are following possibilities :
    a) Current character begins a new subsequence of c’s with bCount subsequences.
    b) Current character is part of cCount subsequences.
    c) Current character is not part of cCount subsequences.
    Therefore we do cCount = (bCount + 2 * cCount);

5) Finally we return cCount;
```cpp
int countSub(string& s)
{
    int acount=0,bcount=0,ccount=0;
    for(int i=0;i<s.size();i++)
    {
        if(s[i]=='a') acount=1+2*acount;
        else if(s[i]=='b') bcount=acount+2*bcount;
        else if(s[i]=='c') ccount=bcount+2*ccount;
    }
    return ccount;
}
```
62. First non-repeating character in a stream
note: it needs the first non-repeating so far. actually we shall maintain a data structure of all those non-repeating char,
When we found a repeat, that one needs goes to top and popped.
use a linked list to easy remove, but hard to find.

63.Find median in a stream
the stored data structure shall be sorted to find the median easily. 
linked list easy to insert, but hard to find.
see leetcode 295
use left and right side heap and keep them balance. left side uses a priority-queue, right side uses a min heap (also a priority-queue)
when a number is added, the number is added to left or right, and we move the top to other side.




























