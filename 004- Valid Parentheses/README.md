<h3> Problem </h3>
Given a string s containing just the characters '(', ')', '{', '}', '[' and ']', determine if the input string is valid.

An input string is valid if:

Open brackets must be closed by the same type of brackets.
Open brackets must be closed in the correct order.
Every close bracket has a corresponding open bracket of the same type.

<pre>
    Input: s = "()[]{}"
    Output: true
</pre>

<h3> Algorithm </h3>
<pre>
Step 1: remove all the opening and closing parenthesis like "()", "{}", "[]".
Step 2: when it's valid then the length of string will automatically become zero and return True.
Step 3: if it's not valid then it'll come out of the loop and return False.
</pre>

<h3> Code in Python </h3>

<pre><code>  def isValid(self, s: str) -> bool:
        count = len(s)
        for i in range(count):
            if "()" in s:
                s = s.replace("()","")
            if "{}" in s:
                s = s.replace("{}","")
            if "[]" in s:
                s = s.replace("[]","")
            if len(s) == 0:
                return True
        else:
            return False </code> </pre>
