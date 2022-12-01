<h3> Problem </h3>
Given a non-empty array of integers nums, every element appears twice except for one. Find that single one.

You must implement a solution with a linear runtime complexity and use only constant extra space.

<pre>
    Input: nums = [2,2,1]
    Output: 1
</pre>

<h3> Algorithm </h3>
<pre>
Step 1: Xor of any two num gives the difference of bit as 1 and same bit as 0.
Step 2: Thus, using this we get 1 ^ 1 == 0 because the same numbers have same bits.
Step 3: So, we will always get the single element because all the same ones will evaluate to 0 and 0^single_number = single_number.
</pre>

<h3> Code in Python </h3>

<pre><code>  def singleNumber(self, nums: List[int]) -> int:
        xor = 0
        for num in nums:
            xor ^= num
        
        return xor </code> </pre>
