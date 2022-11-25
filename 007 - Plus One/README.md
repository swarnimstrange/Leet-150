<h3> Problem </h3>
You are given a large integer represented as an integer array digits, where each digits[i] is the ith digit of the integer. The digits are ordered from most significant to least significant in left-to-right order. The large integer does not contain any leading 0's.

Increment the large integer by one and return the resulting array of digits.

<pre>
    Input: digits = [1,2,3]
    Output: [1,2,4]
    Explanation: The array represents the integer 123.
    Incrementing by one gives 123 + 1 = 124.
    Thus, the result should be [1,2,4].
</pre>

<h3> Algorithm </h3>
<pre>
Step 1: initialize an empty string variable and empty list
Step 2: loop through list and add the elements in str
Step 3: make the str into integer
Step 4: add one to the integer
Step 5: then loop through str of that integer and add the integer of that string into list and then return list.
</pre>

<h3> Code in Python </h3>

<pre><code>  def plusOne(self, digits: List[int]) -> List[int]:
        res = ""
        liss = []
        for i in digits:
            res+=str(i)
        res = int(res) + 1
        for i in str(res):
            liss.append(int(i))
        return liss </code> </pre>
