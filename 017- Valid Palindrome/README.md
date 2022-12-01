<h3> Problem </h3>
A phrase is a palindrome if, after converting all uppercase letters into lowercase letters and removing all non-alphanumeric characters, it reads the same forward and backward. Alphanumeric characters include letters and numbers.

Given a string s, return true if it is a palindrome, or false otherwise.

<pre>
    Input: s = "A man, a plan, a canal: Panama"
    Output: true
    Explanation: "amanaplanacanalpanama" is a palindrome.
</pre>

<h3> Algorithm </h3>
<pre>
Step 1: if the char is numeric or string then save it into a new string.
Step 2: reverse the string and check if it is equal to original and return true.
</pre>

<h3> Code in Python </h3>

<pre><code>  def isPalindrome(self, s: str) -> bool:
        final_string = ""
        for i in s:
            if i.isalpha() or i.isdigit():
                i = i.lower()
                final_string+=i
        reversed_string = final_string[::-1]
        if final_string==reversed_string:
            return True
        else:
            return False </code> </pre>

<h3> Another Solution Algorithm </h3>
<pre>
Step 1: Start with beg = 0 and end = len(s) - 1, the first and the last symbols of string s.
Step 2: Now, we are going to move iterator left only to the right and iterator right only to the left. Let us move them, until we reach alphanumeric symbols, using isalnum() function.
Step 3: Compare these two pointer characters.
</pre>

<h3> Another Code in Python </h3>
<pre><code>  def isPalindrome(self, s: str) -> bool:
        l, r = 0, len(s)-1
        while l < r:
            while l < r and not s[l].isalnum():
                l += 1
            while l < r and not s[r].isalnum():
                r -= 1
            if s[l].lower() != s[r].lower():
                return False
            l +=1; r -= 1
        return True </code> </pre>
