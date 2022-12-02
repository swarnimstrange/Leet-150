<h3> Problem </h3>
Write a function that takes an unsigned integer and returns the number of '1' bits it has (also known as the Hamming weight).

<pre>
    Input: n = 00000000000000000000000000001011
    Output: 3
    Explanation: The input binary string 00000000000000000000000000001011 has a total of three '1' bits.
</pre>

<h3> Algorithm </h3>
<pre>
Step 1: first we check if the right most element is 1 or 0, if it is one we increment a counter
Step 2: then we shift n by 1 to right, and perform the previous action again to check 1 or 0
Step 3: run this loop for 32 times and we'll get our answer
</pre>

<h3> Code in Python </h3>

<pre><code>  def hammingWeight(self, n: int) -> int:
        res = 0
        for i in range(32):
            res += (n & 1)
            n >>= 1
        return res </code> </pre>
