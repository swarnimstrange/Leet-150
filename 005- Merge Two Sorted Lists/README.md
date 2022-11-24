<h3> Problem </h3>
You are given the heads of two sorted linked lists list1 and list2.

Merge the two lists in a one sorted list. The list should be made by splicing together the nodes of the first two lists.

Return the head of the merged linked list.

<pre>
    Input: list1 = [1,2,4], list2 = [1,3,4]
    Output: [1,1,2,3,4,4]
</pre>

<h3> Algorithm </h3>
<pre>
Step 1: initialize dummy new node
Step 2: compare values, if list1 value is greater than list2... add list2 element and increment the pointer forward
Step 3: do the same thing other way round
Step 4: if one list gets over then add the list without comparison
</pre>

<h3> Code in Python </h3>

<pre><code>  def mergeTwoLists(self, list1: Optional[ListNode], list2: Optional[ListNode]) -> Optional[ListNode]:
        dummy = ListNode()
        curr = dummy
        
        while list1 and list2:
            if list1.val < list2.val:
                curr.next = list1
                list1 = list1.next
            else:
                curr.next = list2
                list2 = list2.next
            curr = curr.next
        
        if list1:
            curr.next = list1
        elif list2:
            curr.next = list2
            
        return dummy.next </code> </pre>
