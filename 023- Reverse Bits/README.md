<h3> Problem </h3>
Reverse bits of a given 32 bits unsigned integer.

<pre>
    Input: n = 00000010100101000001111010011100
    Output:    964176192 (00111001011110000010100101000000)
    Explanation: The input binary string 00000010100101000001111010011100 represents the unsigned integer 43261596, so return 964176192 which its binary representation is 00111001011110000010100101000000.
</pre>

<h3> Algorithm </h3>
<pre>
Step 1: Let's work on an example. Say, n = 19, which is 00000000000000000000000000010011 in binary, so in the output we should get 11001000000000000000000000000000 in binary, which is 3355443200.
Step 2: answer << 1 is 00000000000000000000000000000000, n & 1 is 00000000000000000000000000000001 therefore, after + operation answer is 00000000000000000000000000000001
Step 3: then we shift n by 1 to right, therefore we got 1 again at last digit (as we have 0'1'1)
Step 4: answer << 1 is 00000000000000000000000000000010, n & 1 is 00000000000000000000000000000001 therefore, after + operation answer is 00000000000000000000000000000011
Step 5: then we shift n by 1 to right, therefore we got 0 at last digit (as we have '0'11)
Step 6: answer << 1 is 00000000000000000000000000000110, n & 1 is 00000000000000000000000000000000 threfore, after + operation answer is 00000000000000000000000000000110 and so on till 32 digit.
</pre>

<h3> Code in Python </h3>

<pre><code>  def reverseBits(self, n: int) -> int:
        res = 0
        for i in range(32):
            res = (res << 1) + (n & 1)
            n >>= 1
        return res </code> </pre>
