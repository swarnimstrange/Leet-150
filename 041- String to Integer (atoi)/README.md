<h3> Problem </h3>
Implement the myAtoi(string s) function, which converts a string to a 32-bit signed integer (similar to C/C++'s atoi function).

The algorithm for myAtoi(string s) is as follows:

Read in and ignore any leading whitespace.
Check if the next character (if not already at the end of the string) is '-' or '+'. Read this character in if it is either. This determines if the final result is negative or positive respectively. Assume the result is positive if neither is present.
Read in next the characters until the next non-digit character or the end of the input is reached. The rest of the string is ignored.
Convert these digits into an integer (i.e. "123" -> 123, "0032" -> 32). If no digits were read, then the integer is 0. Change the sign as necessary (from step 2).
If the integer is out of the 32-bit signed integer range [-231, 231 - 1], then clamp the integer so that it remains in the range. Specifically, integers less than -231 should be clamped to -231, and integers greater than 231 - 1 should be clamped to 231 - 1.
Return the integer as the final result.
Note:

- Only the space character ' ' is considered a whitespace character.
- Do not ignore any characters other than the leading whitespace or the rest of the string after the digits.

<pre>
    Input: s = "42"
    Output: 42
    Explanation: The underlined characters are what is read in, the caret is the current reader position.
    Step 1: "42" (no characters read because there is no leading whitespace)
            ^
    Step 2: "42" (no characters read because there is neither a '-' nor '+')
            ^
    Step 3: "42" ("42" is read in)
            ^
    The parsed integer is 42.
    Since 42 is in the range [-231, 231 - 1], the final result is 42.
</pre>

<h3> Algorithm </h3>
<pre>
Step 1: remove ' ' from of the string using strip() function.
Step 2: check if the first char string contains numeric values or '+' or '-'.
Step 3: depending on that put flag values to denote signs.
Step 4: if it is numeric values we are gonna change the string to integer using ord(element) - ord("0") -> it gives the exact digit.
Step 5: now that we have got the digit we have to convert the digit into full integer, then let's multiply the digit by 10 and add the front digit to it.
Step 6: for example-: "123" then,
     '1' x 10 = 10
     10 + '2' => '12'
     12 x 10 = 120
     120 + '3' => 123.
Step 7: Once we got our integer, Check for some edge cases like [-2^31, 2^31-1] range and signs of '-' and '+'.
</pre>

<h3> Code in Python </h3>

<pre><code> def myAtoi(self, s: str) -> int:
        flag = 0
        out = 0
        s = s.strip()
        if len(s) == 0:
            return 0
        if s[0] == '-':
            flag = 1
        elif s[0] == '+':
            flag = 2
        elif s[0].isdigit():
                out = ord(s[0]) - ord("0")
                for i in range(1,len(s)):
                    if s[i].isdigit():
                        digit = ord(s[i]) - ord("0")
                        out = out*10 + digit
                    else:
                        break
        if flag == 1 or flag == 2:
            if len(s) != 1:
                if s[1].isdigit():
                    out = ord(s[1]) - ord("0")
                    for i in range(2,len(s)):
                        if s[i].isdigit():
                            digit = ord(s[i]) - ord("0")
                            out = out*10 + digit
                            print(out)
                        else:
                            break
                else:
                    return 0
            else:
                return 0
        if flag == 1 and out <= (2**31):
            return out*(-1)
        elif (flag == 0 or flag == 2) and out <= (2**31-1):
            return out
        elif flag == 1 and out > (2**31):
            return 2**31*(-1)
        elif (flag == 0 or flag == 2) and out > (2**31-1):
            return (2**31)-1
        else:
            return 0 </code> </pre>
