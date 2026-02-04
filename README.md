1. Sliding Window With Sorted Set
This approach uses a SortedSet to maintain a sliding window of up to indexDiff elements (ie.k).
Since the window is kept sorted, we can leverage binary search to efficiently check whether there's a number within valueDiff of the current number.
The algorithm iterates through nums and, for each number, checks whether there is a value within valueDiff in the current window.

If such a number is found, it returns True.
Otherwise, it adds the current number to the SortedSet and removes the leftmost (oldest) one when the window size exceeds indexDiff.
If the entire array is processed without finding such a pair, the function returns False.


2. Sliding Window With Range Bucketing
This approach groups numbers into buckets of size valueDiff + 1 using a hash map (dictionary), while maintaining a sliding window of size indexDiff.
For each number, it checks the current and adjacent buckets for any number within valueDiff.

If such a number is found, it returns True.
Otherwise, it adds the current number to its bucket and removes the number that falls outside the sliding window when the window exceeds indexDiff.
Finally, if no such pair is found after processing all elements, the function returns False.
