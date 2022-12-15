<h3> Problem </h3>
Given a string s, return the longest palindromic substring in s.

<pre>
    Input: s = "babad"
    Output: "bab"
    Explanation: "aba" is also a valid answer.
</pre>

<h3> Algorithm </h3>
<pre>
Step 1: Declare a empty string variable and empty max len variable.
Step 2: Run a loop and find the mid element ( starting from 1st element )
Step 3: Then check for its before and after elements, if both are same update both variable.
Step 4: Keep running the loop till we are getting equal on both side.
Step 5: Compare the maxLen with current window len and update maxLen accordingly.
Step 6: For odd take botg left and right same, for even take both left and right adjacent.
</pre>

<h3> Code in Python </h3>

<pre><code> def longestPalindrome(self, s: str) -> str:
        res = ""
        maxLen = 0
        for i in range(len(s)):
            
            # for odd
            l, r = i, i
            while l >= 0 and r < len(s) and s[l] == s[r]:
                if r-l+1 > maxLen:
                    res = s[l:r+1]
                    maxLen = r - l + 1
                l-=1
                r+=1
            
            # for even
            l, r = i, i+1
            while l >= 0 and r < len(s) and s[l] == s[r]:
                if r-l+1 > maxLen:
                    res = s[l:r+1]
                    maxLen = r - l + 1
                l-=1
                r+=1
        return res </code> </pre>
