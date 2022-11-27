<h3> Problem </h3>
Given the root of a binary tree, check whether it is a mirror of itself (i.e., symmetric around its center).

<img alt="" src="https://assets.leetcode.com/uploads/2021/02/19/symtree1.jpg">

<pre>
    Input: root = [1,2,2,3,4,4,3]
    Output: true
</pre>

<h3> Algorithm </h3>
<pre>
Step 1: Use recursion to traverse nodes of the tree
Step 2: Comapare right and left children of root node 
Step 3: then using recursion take left subtree into one recursion and right subtree into another recursion
Step 4: If both are true that means equal and there's no more node to traverse then return true else return false 
</pre>

<h3> Code in Python </h3>

<pre><code>  def isSymmetric(self, root: Optional[TreeNode]) -> bool:
        if root is None:
            return True
        else:
            return self.iseq(root.left, root.right)
        
    def iseq(self, left, right):
        if left is None and right is None:
            return True
        if left is None or right is None:
            return False
        
        if left.val == right.val:
            out = self.iseq(left.left, right.right)
            ino = self.iseq(left.right, right.left)
            return out and ino
        else:
            return False </code> </pre>
