<h3> Problem </h3>
Given head, the head of a linked list, determine if the linked list has a cycle in it.

There is a cycle in a linked list if there is some node in the list that can be reached again by continuously following the next pointer. Internally, pos is used to denote the index of the node that tail's next pointer is connected to. Note that pos is not passed as a parameter.

Return true if there is a cycle in the linked list. Otherwise, return false.

<pre>
    <img alt="" src="https://assets.leetcode.com/uploads/2018/12/07/circularlinkedlist.png">
    Input: head = [3,2,0,-4], pos = 1
    Output: true
    Explanation: There is a cycle in the linked list, where the tail connects to the 1st node (0-indexed).
</pre>

<h3> Algorithm </h3>
<pre>
Step 1: Keep doing every value None as we traverse.
Step 2: As we stumble upon a cycle we will get the new value as Null which means there's cycle so just return true
Step 3: else if the linked list' head gets empty which means there's no cycle so return False
</pre>

<h3> Code in Python </h3>

<pre><code>  def hasCycle(self, head: Optional[ListNode]) -> bool:
        while head:
            if head.val == None:
                return True
            head.val = None
            head = head.next
        return False </code> </pre>
