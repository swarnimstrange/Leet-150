<h3> Problem </h3>
Given an integer array nums where the elements are sorted in ascending order, convert it to a height-balanced binary search tree.

<img alt="" src="https://assets.leetcode.com/uploads/2021/02/18/btree1.jpg">

<pre>
    Input: nums = [-10,-3,0,5,9]
    Output: [0,-3,9,-10,null,5]
    Explanation: [0,-10,5,null,-3,null,9] is also accepted:
</pre>

<h3> Algorithm </h3>
<pre>
Step 1: Use recursion to traverse nodes of the tree
Step 2: Since nums is a sorted list, the middle element nums[len(nums)//2] must be the root node of nums.
Step 3: Thus, after setting the middle element be the root, finding the middle element in the left subarry nums[:len(nums)//2] and right subarry nums[len(nums)//2 + 1 : ]
</pre>

<h3> Code in Python </h3>

<pre><code>  def sortedArrayToBST(self, nums: List[int]) -> Optional[TreeNode]:
        total_nums = len(nums)
        if not total_nums:
            return None
        mid = total_nums//2
        return TreeNode(
            nums[mid], 
            self.sortedArrayToBST(nums[:mid]), self.sortedArrayToBST(nums[mid+1:])) </code> </pre>
