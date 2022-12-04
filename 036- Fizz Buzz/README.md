<h3> Problem </h3>
Given an integer n, return a string array answer (1-indexed) where:

answer[i] == "FizzBuzz" if i is divisible by 3 and 5.
answer[i] == "Fizz" if i is divisible by 3.
answer[i] == "Buzz" if i is divisible by 5.
answer[i] == i (as a string) if none of the above conditions are true.

<pre>
    Input: n = 3
    Output: ["1","2","Fizz"]
</pre>

<h3> Algorithm </h3>
<pre>
Make an empty array and check for the condition like if divisible from 3 and 5 or just 3 or just 5 or not divisible by any and append the list accordingly.
</pre>

<h3> Code in Python </h3>

<pre><code>  def fizzBuzz(self, n: int) -> List[str]:
        fb = []
        for i in range(1,n+1):
            if i%3==0 and i%5==0:
                fb.append("FizzBuzz")
            elif i%3==0 and i%5!=0:
                fb.append("Fizz")
            elif i%3!=0 and i%5==0:
                fb.append("Buzz")
            else:
                fb.append(str(i))
        return fb </code> </pre>
