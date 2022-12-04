<h3> Problem </h3>
Given an integer n, return true if it is a power of three. Otherwise, return false.

An integer n is a power of three, if there exists an integer x such that n == 3x.

<pre>
    Input: n = 27
    Output: true
    Explanation: 27 = 33
</pre>

<h3> Algorithm </h3>
<pre>
 Run a while loop and keep dividing it by 3 until the number becomes one and then return True.
</pre>

<h3> Code in Python </h3>

<pre><code> def isPowerOfThree(self, n: int) -> bool:
        while n>=1:
            if n==1:
                return True
            n = n/3 </code> </pre>

<h3> Another Algorithm </h3>
<pre>
    Take the largest 3 power number and check if the input number is more than 0 and if it is able to divide directly the largest 3 power or not. If it does that means it's a direct power of 3.
</pre>

<h3> Another Fast Code in Python </h3>

<pre><code>  def isPowerOfThree(self, n: int) -> bool:
        return n > 0 and 1162261467 % n == 0 </code> </pre>
