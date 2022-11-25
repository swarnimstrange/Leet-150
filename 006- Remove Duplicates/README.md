<h3> Problem </h3>
Given an integer array nums sorted in non-decreasing order, remove the duplicates in-place such that each unique element appears only once. The relative order of the elements should be kept the same.

<pre>
    Input: nums = [0,0,1,1,1,2,2,3,3,4]
    Output: 5, nums = [0,1,2,3,4,_,_,_,_,_]
    Explanation: Your function should return k = 5, with the first five elements of nums being 0, 1, 2, 3, and 4 respectively.
    It does not matter what you leave beyond the returned k (hence they are underscores).
</pre>

<h3> Algorithm </h3>
<pre>
Step 1: initialize slow and fast variable
Step 2: run a loop with slow and fast if it's equal then only increment fast variable
Step 3: if not equal then set list value and increment both pointers
Step 4: at last return the size till which we should traverse the list
</pre>

<h3> Code in Python </h3>

<pre><code>  def removeDuplicates(self, nums: List[int]) -> int:
        slow, fast = 0, 1
        while fast in range(len(nums)):
            if nums[slow] == nums[fast]:
                fast += 1
            else:
                nums[slow+1] = nums[fast]
                fast += 1
                slow += 1

        return slow + 1 </code> </pre>
