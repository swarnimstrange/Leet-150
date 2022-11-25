<h3> Problem </h3>
Given a non-negative integer x, return the square root of x rounded down to the nearest integer. The returned integer should be non-negative as well.

You must not use any built-in exponent function or operator.

For example, do not use pow(x, 0.5) in c++ or x \*\* 0.5 in python.

<pre>
    Input: x = 4
    Output: 2
    Explanation: The square root of 4 is 2, so we return 2.
</pre>

<h3> Algorithm </h3>
<pre>
Step 1: Make use of Binary Search in this problem
Step 2: first initialize two pointers left and right
Step 3: left value should be 0 and right value should be the number we are trying to find the square of
Step 4: take mid of left and right and check if it's square is greater of lower than target sqaure number
Step 5: if it's greater, then make right pointer as mid... if it's lower, then make left pointer as mid
Step 6: if the target value is grater or equal to (mid*mid) while being lesser than (mid+1)*(mid+1), then return mid
Step 7: Check for corner cases like if value is 1 or 0.
</pre>

<h3> Code in Python </h3>

<pre><code>  def mySqrt(self, x: int) -> int:
        if x == 1:
            return 1
        l, r = 0, x
        while r > l:
            mid =  (l+r)//2
            if mid*mid <= x < (mid+1)*(mid+1):
                return mid
            elif x < mid * mid:
                r = mid
            else:
                l = mid
        return l </code> </pre>
