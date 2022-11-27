<h3> Problem </h3>
Given the root of a binary tree, return its maximum depth.

A binary tree's maximum depth is the number of nodes along the longest path from the root node down to the farthest leaf node.

<img alt="" src="https://assets.leetcode.com/uploads/2020/11/26/tmp-tree.jpg">

<pre>
    Input: root = [3,9,20,null,null,15,7]
    Output: 3
</pre>

<h3> Algorithm </h3>
<pre>
Step 1: Use recursion to traverse nodes of the tree
Step 2: As we have to find max of the the ways we should use max function with recursion
Step 3: we should put root.left and root.right in recursion as it's binary tree and we should add 1 so that the first depth in counted as 2 and so on..
</pre>

<h3> Code in Python </h3>

<pre><code>  def maxDepth(self, root: Optional[TreeNode]) -> int:
        if root is None:
            return 0
        return max(self.maxDepth(root.left), self.maxDepth(root.right)) +1 </code> </pre>
