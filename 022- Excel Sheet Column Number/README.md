<h3> Problem </h3>
Given a string columnTitle that represents the column title as appears in an Excel sheet, return its corresponding column number.

For example:

<pre>
    A -> 1
    B -> 2
    C -> 3
    ...
    Z -> 26
    AA -> 27
    AB -> 28 
    ...
</pre>

<pre>
    Input: columnTitle = "AB"
    Output: 28
</pre>

<h3> Algorithm </h3>
<pre>
Step 1: Take length of string and loop through it
Step 2: make a variable for sum which represent column number
Step 3: take the ASCII character of the char in loop and convert it to normal alphabet index
Step 4: to find column number for example "ABC". first we take c = 3 then b = 26 * 2 i.e 52 then a = 26 * 26 * 1 i.e 676. if we add all of them we get 676 + 52 + 3 = 731
</pre>

<h3> Code in Python </h3>

<pre><code>  def titleToNumber(self, columnTitle: str) -> int:
        size = len(columnTitle)
        added = 0
        for i in range(len(columnTitle)):
            num = ord(columnTitle[i])-64
            added += (26**((size-1)-i))*num
        return added </code> </pre>
