<h3> Problem </h3>
Given the head of a singly linked list, return true if it is a palindrome or false otherwise.

Follow up: Could you do it in O(n) time and O(1) space?

<pre>
    <img alt="" src="https://assets.leetcode.com/uploads/2021/03/03/pal1linked-list.jpg">
    Input: head = [1,2,2,1]
    Output: true
</pre>

<h3> Algorithm </h3>
<pre>
Step 1: Take two pointers "slow" and "fast". Fast jumps two places and slow jump one place. Therefore, when fast reaches last place slow will be in middle. therefore we got our middle node.
Step 2: Reverse the second part of node.
Step 3: Now go from right to mid and left to mid and compare every element. If any of the element is unequal to each other then return False else True.
</pre>

<h3> Code in Python </h3>

<pre><code>  def isPalindrome(self, head: Optional[ListNode]) -> bool:
        slow = head
        fast = head
        while fast and fast.next is not None:
            slow = slow.next
            fast = fast.next.next
        
        prev = None
        while slow:
            next = slow.next
            slow.next = prev
            prev = slow
            slow = next
        
        left, right = head, prev
        while right:
            if left.val != right.val:
                return False
            left = left.next
            right = right.next
        return True </code> </pre>
