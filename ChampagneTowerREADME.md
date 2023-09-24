# leet-day71

# Champagne Tower Problem

## Problem Description

We stack glasses in a pyramid, where the first row has 1 glass, the second row has 2 glasses, and so on until the 100th row. Each glass holds one cup of champagne.

Then, some champagne is poured into the first glass at the top. When the topmost glass is full, any excess liquid poured will fall equally to the glass immediately to the left and right of it. When those glasses become full, any excess champagne will fall equally to the left and right of those glasses, and so on. (A glass at the bottom row has its excess champagne fall on the floor.)

Given the number of cups poured (`poured`), and the row and glass number of a specific glass (`query_row` and `query_glass`), you need to return how full the specified glass is.

## Example

```cpp
Input: poured = 2, query_row = 1, query_glass = 1
Output: 0.50000
Explanation: We poured 2 cups of champagne to the top glass of the tower (which is indexed as (0, 0)). There is one cup of excess liquid. The glass indexed as (1, 0) and the glass indexed as (1, 1) will share the excess liquid equally, and each will get half a cup of champagne.
```

## Constraints

- 0 <= poured <= 10^9
- 0 <= query_glass <= query_row < 100

## Approach

We can simulate the champagne pouring process step by step. We'll use a 2D vector to represent the glasses and fill them according to the rules mentioned in the problem.

1. Initialize a 2D vector `dp` with dimensions 101x101 to represent the glasses.
2. Pour the `poured` amount of champagne into the top glass (`dp[0][0]`).
3. Iterate through each row and each glass in that row, calculating the overflow and distributing it to the glasses in the row below.
4. Finally, return the amount of champagne in the specified glass (`dp[query_row][query_glass]`).

## Complexity Analysis

The time complexity of this solution is O(query_row^2), which is efficient enough for the given constraints.

