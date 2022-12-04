<h3> Problem </h3>
Given a string s, find the first non-repeating character in it and return its index. If it does not exist, return -1.

<pre>
    Input: s = "leetcode"
    Output: 0
</pre>

<h3> Algorithm </h3>
<pre>
Step 1: Make a Hashmap and store every element and their counts in that.
Step 2: Run a loop and check as the value of any element is 1 which means it's unique so return that.
Step 3: If it comes out of loop then it means it doesn't have any unique element so return -1.
</pre>

<h3> Code in Python </h3>

<pre><code> def firstUniqChar(self, s: str) -> int:
        dict = {}
        for i in s:
            dict[i] = dict.get(i, 0) +1
        for key, i in dict.items():
            if i==1:
                return s.index(key)
        return -1 </code> </pre>

<h3> Another Algorithm </h3>
<pre>
Step 1: Take all letters from A to Z.
Step 2: Check if letter from a to z has any count == 1, if it is then return the minimum index
Step 3: If no count is 1 means no unique element so return -1.
</pre>

<h3> Another Fast Code in Python </h3>

<pre><code>  def firstUniqChar(self, s: str) -> int:
        letters='abcdefghijklmnopqrstuvwxyz'
        index=[s.index(l) for l in letters if s.count(l) == 1]
        return min(index) if len(index) > 0 else -1 </code> </pre>
