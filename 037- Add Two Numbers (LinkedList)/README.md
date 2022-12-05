<h3> Problem </h3>
You are given two non-empty linked lists representing two non-negative integers. The digits are stored in reverse order, and each of their nodes contains a single digit. Add the two numbers and return the sum as a linked list.

You may assume the two numbers do not contain any leading zero, except the number 0 itself.

<pre>
    <img alt="" src="https://assets.leetcode.com/uploads/2020/10/02/addtwonumber1.jpg">
    Input: l1 = [2,4,3], l2 = [5,6,4]
    Output: [7,0,8]
    Explanation: 342 + 465 = 807.
</pre>

<h3> Algorithm </h3>
<pre>
Step 1: first make two string variables and loop through the both linked list and add the values in it.
Step 2: Reverse both strings and add them together and then reverse it.
Step 3: After that one by one convert the string to int and then add it to New Linked List.
</pre>

<h3> Code in Python </h3>

<pre><code> def addTwoNumbers(self, l1: Optional[ListNode], l2: Optional[ListNode]) -> Optional[ListNode]:
        root = l3 = ListNode(0)
        res = ""
        ser = ""
        while l1 is not None:
            res+=str(l1.val)
            l1=l1.next
        while l2 is not None:
            ser+=str(l2.val)
            l2=l2.next
        res = int(res[::-1])
        ser = int(ser[::-1])
        result = res + ser
        result = str(result)
        result = result[::-1]
        i=0
        while i!=len(result):
            val = int(result[i])
            l3.next = ListNode(val)
            l3 = l3.next
            i+=1
        return root.next </code> </pre>

<h3> Another Algorithm </h3>
<pre>
Step 1: Start adding from right side and take carry and add it to left side because we want reversed sum.
Step 2: keep the loop running until the length of linked list or carry is there
Step 3: then take the 1st number of the value and make the Linked List value and add carry to the next value.
Step 4: Once it comes out of loop return Linked List.
</pre>

<h3> Another Fast Code in Python </h3>

<pre><code>  def addTwoNumbers(self, l1: Optional[ListNode], l2: Optional[ListNode]) -> Optional[ListNode]:
        root = l3 = ListNode(0)
        carry = 0
        while l1 or l2 or carry:
            if l1:
                carry += l1.val
                l1 = l1.next
            if l2:
                carry +=l2.val
                l2 = l2.next
            l3.next = ListNode(carry%10)
            l3 = l3.next
            carry //= 10
        return root.next </code> </pre>
