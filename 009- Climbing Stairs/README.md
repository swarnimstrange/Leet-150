<h3> Problem </h3>
You are climbing a staircase. It takes n steps to reach the top.

Each time you can either climb 1 or 2 steps. In how many distinct ways can you climb to the top?

<pre>
    Input: n = 3
    Output: 3
    Explanation: There are three ways to climb to the top.
    1. 1 step + 1 step + 1 step
    2. 1 step + 2 steps
    3. 2 steps + 1 step
</pre>

<h3> Algorithm </h3>
<pre>
Step 1: Using bottom up approach for this problem
Step 2: start with the base case and make two pointers
Step 3: as we go further we would store the number of ways in two pointers...that is if we jumped one stairs it will be stored in "one" variable and two stairs will be stored in "two" variable.
Step 4: then we move the pointer forward by making the sum of both "one" and "two" equal to "one" and the old "one" variable equal to "two".
Step 5: when there's no more elements in loop just return the sum of last two pointers
</pre>

<h3> Code in Python </h3>

<pre><code>  def climbStairs(self, n: int) -> int:
        one, two = 1, 1
        for i in range(n-1):
            temp = one
            one = one + two
            two = temp
        return one </code> </pre>
