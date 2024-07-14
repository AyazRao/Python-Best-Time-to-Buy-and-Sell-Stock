# Best Time to Buy and Sell Stock

## Description

You are given an array `prices` where `prices[i]` is the price of a given stock on the `i`th day.

You want to maximize your profit by choosing a single day to buy one stock and choosing a different day in the future to sell that stock.

Return the maximum profit you can achieve from this transaction. If you cannot achieve any profit, return 0.

## Constraints

- `1 <= prices.length <= 10^5`
- `0 <= prices[i] <= 10^4`

## Intuition

To solve this problem, you need to compare each price with the previous prices to identify the lowest value to buy the stock. Then, you will look for the next higher values to sell the stock and calculate the profit. By doing this, you can determine the maximum profit.

## Approach

1. Initialize `profit` to 0.
2. Initialize `buying_price` to the first value in the list of prices.
3. Loop over the list of prices:
    - If a price is found that is less than the current `buying_price`:
        - Update `buying_price` to this new lower price.
    - Calculate the profit using the current price minus the `buying_price`.
    - If this calculated profit is greater than the current profit:
        - Update `profit` to this new higher profit.
4. After iterating through all the prices, the final value of `profit` will be the maximum profit.

## Complexity

### Time Complexity

The time complexity of the `maxProfit` function can be analyzed by examining the loops and operations within the function:

- The `for` loop runs from `i = 1` to `len(prices) - 1`, iterating over the list of prices exactly once.
- Each operation inside the loop (comparisons and assignments) takes constant time, `O(1)`.
- Since the loop iterates `n - 1` times (where `n` is the length of the prices list), the overall time complexity is `O(n)`.

### Space Complexity

The space complexity of the `maxProfit` function can be analyzed by examining the additional space required by the function:

- The space used is primarily for a few integer variables (`profit` and `buy`), which take up constant space, `O(1)`.
- No additional data structures that grow with input size are used.
- Hence, the space complexity is `O(1)`.

## Code

```python
class Solution(object):

    def maxProfit(self, prices):
        """
        :type prices: List[int]
        :rtype: int
        """
        profit = 0
        buy = prices[0]
        for i in range(1, len(prices)):            
            if prices[i] < buy:     
                buy = prices[i]
            if prices[i] - buy > profit:
                profit = prices[i] - buy
        return profit
```
## Installation

To run the code, ensure you have Python installed on your system. Save the code in a `.py` file and execute it using a Python interpreter.

## Usage

To use the function, create an instance of the `Solution` class and call the `maxProfit` method with your list of prices.

## Example

```python
prices = [7, 1, 5, 3, 6, 4]
solution = Solution()
print(solution.maxProfit(prices))  # Output: 5
```
## Contributing
If you'd like to contribute, please fork the repository and use a feature branch. Pull requests are warmly welcome.

## Acknowledgements
Thanks to the open-source community for providing helpful resources and inspiration. Special thanks to [LeetCode](https://leetcode.com) for the platform and resources.

# LeetCode Submission
You can view my LeetCode submission for this problem [here](https://leetcode.com/problems/best-time-to-buy-and-sell-stock/solutions/5474986/python-best-time-to-buy-and-sell-stock)
.
