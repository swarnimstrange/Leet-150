<h3> Problem </h3>
Given an integer array nums, return true if any value appears at least twice in the array, and return false if every element is distinct.

<pre>
    Input: nums = [1,2,3,1]
    Output: true
</pre>

<h3> Algorithm </h3>
<pre>
Step 1: Sort the array and Iterate through a loop 
Step 2: Check if the previous element is equal to current element
Step 3: If it is equal return True else False
</pre>

<h3> Code in Python </h3>

<pre><code>  def containsDuplicate(self, nums: List[int]) -> bool:
        nums.sort()
        for i in range(1,len(nums)):
            if nums[i] == nums[i-1]:
                return True
        return False </code> </pre>
