<h3> Problem </h3>
Write a function that reverses a string. The input string is given as an array of characters s.

You must do this by modifying the input array in-place with O(1) extra memory.

<pre>
    Input: s = ["h","e","l","l","o"]
    Output: ["o","l","l","e","h"]
</pre>

<h3> Algorithm </h3>
<pre>
Step 1: Take two pointers start and end.
Step 2: Loop until end is greater than start and keep swapping elements.
Step 3: Once it comes out of loop our string is reversed.
</pre>

<h3> Code in Python </h3>

<pre><code>  def reverseString(self, s: List[str]) -> None:
        """
        Do not return anything, modify s in-place instead.
        """
        start = 0
        end = len(s)-1
        while start < end:
            s[start], s[end] = s[end], s[start]
            start += 1
            end-=1 </code> </pre>
