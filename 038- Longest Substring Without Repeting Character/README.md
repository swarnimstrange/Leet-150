<h3> Problem </h3>
Given a string s, find the length of the longest substring without repeating characters.

<pre>
    Input: s = "abcabcbb"
    Output: 3
    Explanation: The answer is "abc", with the length of 3.
</pre>

<h3> Algorithm </h3>
<pre>
Step 1: Make a set and declare left variable
Step 2: Run a loop and check if the right pointer is present in set or not
Step 3: if right pointer element is present then remove the left pointer element and increment left pointer
Step 4: add the right pointer element to set and then find out the maximum of the current window size or previous one
Step 5: at last we'll get the longest substring.
</pre>

<h3> Code in Python </h3>

<pre><code> def lengthOfLongestSubstring(self, s: str) -> int:
        sset = set()
        l = 0
        res = 0
        for r in range(len(s)):
            while s[r] in sset:
                sset.remove(s[l])
                l+=1
            sset.add(s[r])
            res = max(res, r-l+1)
        return res </code> </pre>
