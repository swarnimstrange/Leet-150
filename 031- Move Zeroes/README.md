<h3> Problem </h3>
Given an integer array nums, move all 0's to the end of it while maintaining the relative order of the non-zero elements.

Note that you must do this in-place without making a copy of the array.

<pre>
    Input: nums = [0,1,0,3,12]
    Output: [1,3,12,0,0]
</pre>

<h3> Algorithm </h3>
<pre>
Step 1: make two variables one from start and other from end.
Step 2: iterate until start index is less than end index
Step 3: if we find any element to be zero then we remove that zero from index position and append it at last
Step 4: Once we appended we decrease the end counter else we increase the start counter to find zeroes
</pre>

<h3> Code in Python </h3>

<pre><code> def moveZeroes(self, nums: List[int]) -> None:
        i = 0
        end = len(nums)
        while i < end:
            if nums[i] == 0:
                del nums[i]
                nums.append(0)
                end -= 1
            else:
                i += 1 </code> </pre>

<h3> Another Algorithm </h3>
<pre>
    Swap all the non zero elements one by one at starting indexes so that all zero elements will be placed at last.
</pre>

<h3> Another Fast Code in Python </h3>

<pre><code>  def moveZeroes(self, nums: List[int]) -> None:
        i = 0
        for j in range(len(nums)):
            if nums[j] != 0:
                nums[i], nums[j] = nums[j], nums[i]
                i += 1 </code> </pre>
