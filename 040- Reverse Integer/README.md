<h3> Problem </h3>
Given a signed 32-bit integer x, return x with its digits reversed. If reversing x causes the value to go outside the signed 32-bit integer range [-231, 231 - 1], then return 0.

Assume the environment does not allow you to store 64-bit integers (signed or unsigned).

<pre>
    Input: x = -123
    Output: -321
</pre>

<h3> Algorithm </h3>
<pre>
Step 1: Convert int to string and if first char is '-' then set flag to 1 and take all digits into string after the char
Step 2: Now reverse the string
Step 3: if flag is 1 then it means it was negetive so we'll put '-' before digits
Step 4: else we would return the digits as it is.
</pre>

<h3> Code in Python </h3>

<pre><code> def reverse(self, x: int) -> int:
        s = str(x)
        flag = 0
        if s[0] == '-':
            flag = 1
            s = s[1:]
        s = s[::-1]
        xi = int(s)
        if flag == 1:
            xi = '-' + str(xi)
            xi = int(xi)
        if xi >= (2**31 -1) or xi <= -2**31:
            return 0
        else:
            return xi </code> </pre>
