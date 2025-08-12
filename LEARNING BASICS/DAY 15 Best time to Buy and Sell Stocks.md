You are given an array `prices` 
- where `prices[i]` is the price of a given stock on the `ith` day.

You want to maximize your profit 
- by choosing a **single day** to buy one stock and 
- choosing a **different day in the future** to sell that stock.

Return _the maximum profit you can achieve from this transaction_. If you cannot achieve any profit, return `0`.

**Example 1:**

**Input:** prices = [7,1,5,3,6,4]
**Output:** 5
**Explanation:** Buy on day 2 (price = 1) and sell on day 5 (price = 6), profit = 6-1 = 5.
Note that buying on day 2 and selling on day 1 is not allowed because you must buy before you sell.

**Example 2:**

**Input:** prices = [7,6,4,3,1]
**Output:** 0
**Explanation:** In this case, no transactions are done and the max profit = 0.

**Constraints:**

- `1 <= prices.length <= 105`
- `0 <= prices[i] <= 104`

# My Solution 
- Wanted to find Lowest first 
- Search for Highest starting from the lowest
```js
function fun(prices) {
if (prices.length < 2) return 0;
let low = +Infinity;
let high = -Infinity;
for (let i = 0; i < prices.length; i++) {
  if (prices[i] < low) {
    low = prices[i];
    if (i == prices.length - 1) {
      return 0;
    }
    high = 0;
    for (let j = i + 1; j < prices.length; j++) {
      if (prices[j] > high) {
        high = prices[j];
      }
    }
  }
}
let profit = high - low;
return profit;
}

//let prices = [7,6,4,3,1] //0
//let prices = [7, 1, 5, 3, 6, 4] //5
//let prices = [4,9,1,8] //7
//let prices = [0,5,9] //9
//let prices =[3,3,3,3]
//let prices = []
let k = fun(prices);
console.log(k);

```
- Unfortunately this is O(n)at best and O(n2) at the worst
- Space Complexity is O(1)

```js 
function maxProfit(prices) {
  let lastbuy = +Infinity;
  let profit = 0;
  for (let todayprice of prices) {
    if (todayprice < lastbuy) lastbuy = todayprice;
    let diff = todayprice - lastbuy;
    if (diff > profit) profit = diff;
  }
  return profit;
}

//let prices = [7,6,4,3,1] //0
//let prices = [7, 1, 5, 3, 6, 4] //5
//let prices = [4,9,1,8] //7
//let prices = [0,5,9] //9
//let prices =[3,3,3,3]
//let prices = []
let k = maxProfit(prices);
console.log(k);
```

# logic behind this code above
### Step 1 — What we want
We have a list of prices of lemons each day.  
We want to buy lemons **on the cheapest day** and sell them **on a later, more expensive day** to make the most money.

---
### Step 2 — Our “brain rules”
We need to remember two things while going through each day’s price:

1. **lowest** → the cheapest lemons we’ve seen so far (best day to buy).
    
2. **best** → the biggest profit we’ve made so far.

---
### Step 3 — The loop
We walk through the days, one by one, and do this:

**(a) Did we find cheaper lemons today?**  
If **yes**, we update our “cheapest price” because maybe this is a better day to buy.

**(b) If we sell today, what profit do we make?**  
Profit = today’s price − cheapest price we’ve seen before.

**(c) Is that profit bigger than our “best” profit so far?**  
If **yes**, we update the “best” profit.

---
### Step 4 — Why it works
Because we always:
- Buy at the cheapest day so far.
    
- Check if selling today gives us a better profit.
    
- Never sell before we buy (since cheapest day is always before or same day).![[output 1.png]]