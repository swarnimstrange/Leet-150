<h3> Problem </h3>
Write an algorithm to determine if a number n is happy.

A happy number is a number defined by the following process:

Starting with any positive integer, replace the number by the sum of the squares of its digits.
Repeat the process until the number equals 1 (where it will stay), or it loops endlessly in a cycle which does not include 1.
Those numbers for which this process ends in 1 are happy.
Return true if n is a happy number, and false if not.

<pre>
    Input: n = 19
    Output: true
    Explanation:
    12 + 92 = 82
    82 + 22 = 68
    62 + 82 = 100
    12 + 02 + 02 = 1
</pre>

<h3> Algorithm </h3>
<pre>
Step 1: Only one digit numbers which returns 1 on adding it's digits are 1 and 7. So, if the results are except it then return False
Step 2: take every digit of a number and square it and add it to a variable
Step 3: keep the while loop running until the the sum of square of digits becomes 1.
</pre>

<h3> Code in Python </h3>

<pre><code>  def isHappy(self, n: int) -> bool:
        while n!=1:
            added = 0
            if n==2 or n==3 or n==4 or n==5 or n==6 or n==8 or n==9:
                return False
            while n!=0:
                sin = n%10
                added += sin**2
                n//=10
            n = added
        return True </code> </pre>
