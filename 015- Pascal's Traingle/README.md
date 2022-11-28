<h3> Problem </h3>
Given an integer numRows, return the first numRows of Pascal's triangle.

In Pascal's triangle, each number is the sum of the two numbers directly above it as shown:

<img alt="" src="https://upload.wikimedia.org/wikipedia/commons/0/0d/PascalTriangleAnimated2.gif">

<pre>
    Input: numRows = 5
    Output: [[1],[1,1],[1,2,1],[1,3,3,1],[1,4,6,4,1]]
</pre>

<h3> Algorithm </h3>
<pre>
Step 1: As we can see that every element is added with it's forward element to give a new element of new list.
Step 2: For example we have [1,2,1], so (1 and 2) are added to give "3" and (2 and 1) are added to give "3" as well. so the new list's middle would be 3,3 and later we can insert 1 in beginning and 1 in last. and we'll get the next list.
Step 3: So we can form [1,3,3,1] from [1,2,1] and so on.
</pre>

<h3> My Code in Python </h3>

<pre><code>  def generate(self, numRows: int) -> List[List[int]]:
        res = []
        res.append([1])
        if numRows==1:
            return res
        res.append([1,1])
        for i in range(numRows-2):
            nums = []
            last_array = res[-1]
            lent = len(last_array)
            last_ind = lent-2
            if last_ind==0:
                nums.append(sum(last_array[0:2]))
            else:
                for i in range(last_ind+1):
                    nums.append(sum(last_array[i:i+2]))
            nums.insert(0, 1)
            nums.insert(len(nums), 1)
            res.append(nums)
        return res </code> </pre>

<h3>Simple Algorithm </h3>
<pre>
Step 1: if array's are shifted by one place and added to each other we can get the next list
Step 2: for example-:
        [1, 2, 1]
        +  [1, 2, 1]
        [1, 3, 3, 1]   -> next array and so on..
</pre>

<h3> Code in Python </h3>

<pre><code>  def generate(self, numRows: int) -> List[List[int]]:
        res = [[1]]
        for i in range(1, numRows):
            temp1 = res[-1] + [0]
            temp2 = [0] + res[-1]
            res.append([temp1[i]+temp2[i] for i in range(len(temp1))])
        return res[:numRows] </code> </pre>
