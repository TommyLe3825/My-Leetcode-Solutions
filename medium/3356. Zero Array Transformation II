class Solution:
    def minZeroArray(self, nums: List[int], queries: List[List[int]]) -> int:
        # Initialize binary search boundaries
        left, right = 0, len(queries)  
        
        # Step 1: First check if it's even possible to zero the array using ALL queries
        # If not possible even after using all queries → return -1 early
        if not self.can_form_zero_array(nums, queries, right):
            return -1

        # Step 2: Binary search to find the smallest k that works
        while left <= right:
            middle = left + (right - left) // 2  # Find middle point
            
            # Try using the first `middle` queries to see if it works
            if self.can_form_zero_array(nums, queries, middle):
                # If it works, try a smaller k (move left)
                right = middle - 1
            else:
                # If it fails, try a larger k (move right)
                left = middle + 1

        # Step 3: Return the smallest successful k value
        return left

    def can_form_zero_array(self, nums: List[int], queries: List[List[int]], k: int) -> bool:
        n = len(nums)  # Length of nums array
        total_sum = 0  # Running sum to compute final effect of queries
        
        # Initialize a difference array of size n + 1 (extra space to handle boundary)
        difference = [0] * (n + 1)
        
        # Step 1: Apply first k queries using difference array technique
        for i in range(k):
            start, end, val = queries[i]  
            
            # Start reducing from index `start`
            difference[start] += val
            
            # Stop reducing after index `end`
            difference[end + 1] -= val
        
        # Step 2: Build the resulting array using prefix sum of difference array
        for i in range(n):
            # Compute the net effect at index `i`
            total_sum += difference[i]
            
        #Checking each nums[i] is greater
        #If not, total_sum is greater in that case which wouldn't work
            if total_sum < nums[i]:
                return False
        
        # Step 3: If ALL elements in nums are reduced to zero or less → Success!
        return True
