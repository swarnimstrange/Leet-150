<h3> Problem </h3>
Given the root of a binary tree, return the inorder traversal of its nodes' values.

<img alt="" src="https://assets.leetcode.com/uploads/2020/09/15/inorder_1.jpg style="width: 202px; height: 324px;">

<pre>
    Input: root = [1,null,2,3]
    Output: [1,3,2]
</pre>

<h3> Algorithm </h3>
<pre>
Step 1: just remember the chronology of inorder that is left -> root -> right
Step 2: Use recursion so that it reaches the most left element then print its value 
Step 3: then recursion will go back so it'll print root then
Step 4: after than just recurse through right branch of the tree 
</pre>

<h3> Code in Python </h3>

<pre><code>  def inorderTraversal(self, root: Optional[TreeNode]) -> List[int]:
        list = []
        self.Traversal(root, list)
        return list
    
    def Traversal(self, root, list):
        if root:
            self.Traversal(root.left, list)
            list.append(root.val)
            self.Traversal(root.right, list) </code> </pre>
