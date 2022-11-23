Roman numerals are represented by seven different symbols: I, V, X, L, C, D and M.

<pre>
    Symbol       Value
    I             1
    V             5
    X             10
    L             50
    C             100
    D             500
    M             1000

    I can be placed before V (5) and X (10) to make 4 and 9. 
    X can be placed before L (50) and C (100) to make 40 and 90. 
    C can be placed before D (500) and M (1000) to make 400 and 900.
</pre>

Given a roman numeral, convert it to an integer.

<pre>
    Input: s = "MCMXCIV"
    Output: 1994
    Explanation: M = 1000, CM = 900, XC = 90 and IV = 4.
</pre>

<pre>
<code>
    def romanToInt(self, s: str) -> int:
        sum = 0
        my_dict = {
            "I" : 1,
            "V" : 5,
            "X" : 10,
            "L" : 50,
            "C" : 100,
            "D" : 500,
            "M" : 1000
        }
        s = s.replace("IV","IIII")
        s = s.replace("IX","VIIII")
        s = s.replace("XL","XXXX")
        s = s.replace("XC","LXXXX")
        s = s.replace("CD","CCCC")
        s = s.replace("CM","DCCCC")
        
        for i in s:
            sum += my_dict[i]
            
        return sum
</code>
</pre>
