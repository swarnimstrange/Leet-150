<h3> Problem </h3>
Given an array nums of size n, return the majority element.

The majority element is the element that appears more than ⌊n / 2⌋ times. You may assume that the majority element always exists in the array.

<pre>
    Input: nums = [2,2,1,1,1,2,2]
    Output: 2
</pre>

<h3> Algorithm </h3>
<pre>
Step 1: Take count every element in list
Step 2: Find the maximum count of a element in list
Step 3: check wheather it more than len(nums)/2
Step 4: if it is return the index
</pre>

<h3> Code in Python </h3>

<pre><code>  uniq = set(nums)
        max_count = 0
        for i in uniq:
            curr_count = nums.count(i)
            if curr_count > max_count:
                max_count=curr_count
            if max_count > len(nums)/2:
                return i </code> </pre>
