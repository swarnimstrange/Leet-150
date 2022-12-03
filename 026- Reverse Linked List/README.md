<h3> Problem </h3>
Given the head of a singly linked list, reverse the list, and return the reversed list.

<pre>
    <img alt="" src="https://assets.leetcode.com/uploads/2021/02/19/rev1ex1.jpg">
    Input: head = [1,2,3,4,5]
    Output: [5,4,3,2,1]
</pre>

<h3> Algorithm </h3>
<pre>
<img alt="" src="https://media.geeksforgeeks.org/wp-content/cdn-uploads/RGIF2.gif" width = "300" height = "300">
Step 1: Initialize  three pointers prev as NULL, curr as head, and next as NULL.
Step 2: Iterate through Linked List and Before changing the next of curr, store the next node (next = curr.next)
Step 3: Now update the next pointer of curr to the prev (curr.next = prev)
Step 4: Update prev as curr and curr as next (prev = curr, curr = next)
</pre>

<h3> Code in Python </h3>

<pre><code>  def reverseList(self, head: Optional[ListNode]) -> Optional[ListNode]:
        prev = None
        current = head
        while(current is not None):
            next = current.next
            current.next = prev
            prev = current
            current = next
        return prev </code> </pre>
