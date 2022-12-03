<h3> Problem </h3>
You are given an array prices where prices[i] is the price of a given stock on the ith day.

You want to maximize your profit by choosing a single day to buy one stock and choosing a different day in the future to sell that stock.

Return the maximum profit you can achieve from this transaction. If you cannot achieve any profit, return 0.

<pre>
    Input: prices = [7,1,5,3,6,4]
    Output: 5
    Explanation: Buy on day 2 (price = 1) and sell on day 5 (price = 6), profit = 6-1 = 5.
    Note that buying on day 2 and selling on day 1 is not allowed because you must buy before you sell.
</pre>

<h3> Algorithm </h3>
<pre>
Step 1: Let us initialize Left and Right pointer to first and second position of array, Left is to buy stock and Right is to sell stock
Step 2: If price[left] is greater than price[right] then we will move left pointer to the right position and increment our right pointer by 1.
Step 3: If price[left] is less than price[right] which means we will get profit so we will update our max profit and move our right by 1.
Step 4: As we reach the end of the list we'll get our max profit that we need to return.
</pre>

<h3> Code in Python </h3>

<pre><code>  def maxProfit(self, prices: List[int]) -> int:
        left=0
        right = 1
        maximum = 0
        while right < len(prices):
            if prices[left]>prices[right]:
                left = right
            else:
                curr = prices[right]-prices[left]
                maximum = max(curr, maximum)
            right+=1
        return maximum </code> </pre>
