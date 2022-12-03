<h3> Problem </h3>
Given an array nums containing n distinct numbers in the range [0, n], return the only number in the range that is missing from the array.

<pre>
    Input: nums = [3,0,1]
    Output: 2
    Explanation: n = 3 since there are 3 numbers, so all numbers are in the range [0,3]. 2 is the missing number in the range since it does not appear in nums.
</pre>

<h3> Algorithm </h3>
<pre>
Step 1: Take the sum of all element till length ( suppose 3 => 0+1+2+3 = 6 ) 
Step 2: Now take the sum of given array
Step 3: subtract length sum with sum of array.
</pre>

<h3> Code in Python </h3>

<pre><code>  def missingNumber(self, nums: List[int]) -> int:
        n = len(nums)
        return ((n * (n+1)) // 2)-sum(nums) </code> </pre>
