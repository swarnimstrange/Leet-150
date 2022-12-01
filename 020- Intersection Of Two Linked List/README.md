<h3> Problem </h3>
Given the heads of two singly linked-lists headA and headB, return the node at which the two lists intersect. If the two linked lists have no intersection at all, return null.

<pre>
    <img alt="" src="https://assets.leetcode.com/uploads/2021/03/05/160_example_1_1.png">
    Input: intersectVal = 8, listA = [4,1,8,4,5], listB = [5,6,1,8,4,5], skipA = 2, skipB = 3
    Output: Intersected at '8'
    Explanation: The intersected node's value is 8 (note that this must not be 0 if the two lists intersect).
    From the head of A, it reads as [4,1,8,4,5]. From the head of B, it reads as [5,6,1,8,4,5]. There are 2 nodes before the intersected node in A; There are 3 nodes before the intersected node in B.
    - Note that the intersected node's value is not 1 because the nodes with value 1 in A and B (2nd node in A and 3rd node in B) are different node references. In other words, they point to two different locations in memory, while the nodes with value 8 in A and B (3rd node in A and 4th node in B) point to the same location in memory.
</pre>

<h3> Algorithm </h3>
<pre>
Step 1: Find a way to line up the ends of the two lists.
Step 2: The easiest way to do that is to concatenate them in opposite orders, A+B and B+A
Step 3: This way, the ends of the two original lists will align on the second half of each merged list.
Step 4: Then we just need to check if at some point the two merged lists are pointing to the same node
<img alt="" src="https://i.imgur.com/hcpocCV.png">
<img alt="" src="https://i.imgur.com/dDUjSPk.png">
</pre>

<h3> Code in Python </h3>

<pre><code>  def getIntersectionNode(self, headA: ListNode, headB: ListNode) -> Optional[ListNode]:
        l1, l2 = headA, headB
        while l1!=l2:
            l1 = l1.next if l1 else headB
            l2 = l2.next if l2 else headA
        return l1 </code> </pre>
