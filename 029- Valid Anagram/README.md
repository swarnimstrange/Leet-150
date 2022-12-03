<h3> Problem </h3>
Given two strings s and t, return true if t is an anagram of s, and false otherwise.

An Anagram is a word or phrase formed by rearranging the letters of a different word or phrase, typically using all the original letters exactly once.

<pre>
    Input: s = "anagram", t = "nagaram"
    Output: true
</pre>

<h3> Algorithm </h3>
<pre>
Sort both strings and check if both are equal
</pre>

<h3> Code in Python </h3>

<pre><code>  def isAnagram(self, s: str, t: str) -> bool:
        s = ''.join(sorted(s))
        t = ''.join(sorted(t))
        if s==t:
            return True
        else:
            return False </code> </pre>

<h3> Another Algorithm </h3>
<pre>
    for elements from 'a' to 'z' compare their count in both strings and return True if equal
</pre>

<h3> Another Fast Code in Python </h3>

<pre><code>  def isAnagram(self, s: str, t: str) -> bool:
        for x in 'abcdefghijklmnopqrstuvwxzy':
            if s.count(x) != t.count(x):
                return False
        return True </code> </pre>
