<h3> Problem </h3>
Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to target.

You may assume that each input would have exactly one solution, and you may not use the same element twice.

You can return the answer in any order.

<pre>
    Input: nums = [2,7,11,15], target = 9
    Output: [0,1]
    Explanation: Because nums[0] + nums[1] == 9, we return [0, 1].
</pre>

<h3> Algorithm </h3>
make an embedded loop and check if any of the sum is equal to target if it is return the indexes of elements

<h3> Code in Python</h3>

<pre><code> def twoSum(self, nums: List[int], target: int) -> List[int]:
        for i in range(len(nums)):
            for j in range(i):
                if nums[i]+nums[j] == target:
                    return j,i </code></pre>
