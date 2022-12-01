<h3> Problem </h3>
Write a function to find the longest common prefix string amongst an array of strings.

If there is no common prefix, return an empty string "".

<pre>
    Input: strs = ["flower","flow","flight"]
    Output: "fl"
</pre>

<h3> Algorithm </h3>
<pre>
Step 1: initialize empty str variable "result"
Step 2: loop through shortest string length 
Step 3: loop through each strings in list and compare their values with the shortest one
Step 4: if loop reaches the length of shortest string or the values aren't equal anymore then return result
Step 5: if the chars are equal just add the char to "result"
Step 6: return result at end 
</pre>

<h3> Code in Python </h3>

<pre><code> def longestCommonPrefix(self, strs: List[str]) -> str:
        res = ""
        short = min(strs,key=len)
        for i in range(len(short)):
            for s in strs:
                if i == len(short) or s[i]!=short[i]:
                    return res
            res+=s[i]
        return res </code> </pre>
