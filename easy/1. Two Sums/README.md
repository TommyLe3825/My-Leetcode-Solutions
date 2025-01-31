**1. Two Sums**
Understanding the problem – What is it asking?
Initial approach – How did you first think about solving it?
Challenges faced – Did you struggle with anything?
Final solution – What approach did you use, and why?
Key takeaways – What did you learn that will help in future problems?

Time Complexity – How efficient is your solution?
Space Complexity – How much extra memory does it use?
Algorithm Used – Brute force, hash map, two pointers, sorting, etc.
Why This Approach? – Justify why your chosen solution is optimal.

Link to the Leetcode problem: Two Sum - LeetCode

Neetcode’s video lead me to my answer so check him out please: Two Sum - Leetcode 1 - HashMap - Python

Understanding the problem:
I’m a bit rusty on programming but I believe it’s saying to find two numbers in our array given to get our target value
We shall return those two numbers that add up to the target

Initial approach:
The initial idea was to basically keep a value in the array and then test it out with the rest and continue from there.

Challenges faced:
From watching Neetcode’s video, it seems that my initial approach would work as it is a Brute Force algorithm but not the most optimal
It would work but as described in his video, it would be a runtime of O(n^2)

Neetcode’s Approach:
He created a hashmap and assigned each value to the index of each value

He then has the target which in his video was 4 subtracted by the first value in index 0 which is 2
4 - 2 = 2
We then use the answer to find the value in the array but we aren’t allowed to use the same one since they are both from the same index
I’m starting to see what’s happening
He is doing a One Pass algorithm
He basically starts with a empty hash map and goes to array and subtracts the target by the value at the current array index.
He continues going through and at index 1, he got 3 which does exist in the array but he continues to go down
It eventually hits index 3 in the array and once he checks for the value of 1 since 4-3 equals 1, it’s at index 1

We then return their indices which would be [1,3] in this case which works


Why it works (One Pass):
Explained by Neetcode
If we start with a big array, we know there are two elements that sum into our target value
We just don’t know the location of it

We will start iterating through the array as we fill up our hash map

As we continue updating, we will eventually hit the first solution and the second solution, and once we hit the second solution, we guarantee the first solution 
It is a constant time operation since we are adding each value to the hash map as we go through the array as we pass by once
As well as checking if a value exists in our hash map all in constant time
Time complexity: O(n)

Memory will be extra for the hash map and there is a chance we have to add every value to the hash map
Space complexity: O(n)

Key Takeaways:
Enumerate function adds a counter to an iterable(like a list, tuple, or string) and returns it as an enumerate object
It is especially useful in loops when you need both the index and value of each element


