<h3> Problem </h3>
You are given two integer arrays nums1 and nums2, sorted in non-decreasing order, and two integers m and n, representing the number of elements in nums1 and nums2 respectively.

Merge nums1 and nums2 into a single array sorted in non-decreasing order.

The final sorted array should not be returned by the function, but instead be stored inside the array nums1. To accommodate this, nums1 has a length of m + n, where the first m elements denote the elements that should be merged, and the last n elements are set to 0 and should be ignored. nums2 has a length of n.

<pre>
    Input: nums1 = [1,2,3,0,0,0], m = 3, nums2 = [2,5,6], n = 3
    Output: [1,2,2,3,5,6]
    Explanation: The arrays we are merging are [1,2,3] and [2,5,6].
    The result of the merge is [1,2,2,3,5,6] with the underlined elements coming from nums1.
</pre>

<h3> Algorithm </h3>
<pre>
Step 1: Find the real size of the nums1 array
Step 2: Substract n from len(nums1) 
Step 3: all the zeros in nums1 are of in n numbers
Step 4: So, replace all the zeros from nums1 with nums2 values
Step 5: once replaced the zeros sort the array.
Step 6: handle some corner cases like size == m: then return nums1 and size == n: then replace all elements in nums1 with nums2
</pre>

<h3> Code in Python </h3>

<pre><code>  def merge(self, nums1: List[int], m: int, nums2: List[int], n: int) -> None:
        """
        Do not return anything, modify nums1 in-place instead.
        """
        size = len(nums1)
        if size == m:
            return nums1
        if size == n:
            nums1[:] = nums2
        else:
            nums1[(size-n):] = nums2
            nums1.sort() </code> </pre>
