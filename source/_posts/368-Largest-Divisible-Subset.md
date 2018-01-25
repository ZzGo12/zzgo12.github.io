---
title: 368. Largest Divisible Subset
date: 2018-01-03 21:16:17
tags: [Math,Dynamic Programming]
categories: leetcode
---


{% blockquote  leetcode https://leetcode.com/problems/largest-divisible-subset/description/ 368. Largest Divisible Subset %}
题目描述如下：
Given a set of distinct positive integers, find the largest subset such that every pair (Si, Sj) of elements in this subset satisfies: Si % Sj = 0 or Sj % Si = 0.

If there are multiple solutions, return any subset is fine.

Example 1:

    nums: [1,2,3]

    Result: [1,2] (of course, [1,3] will also be ok)

Example 2:

    nums: [1,2,4,8]

    Result: [1,2,4,8]


{% endblockquote %}

---

## 解题思路：

1. 自己的思路是按层次筛选。 先排个序, 然后按层次遍历出可能的subset。 由题意可知， 第一层若是X， 下一层为X的倍数， 再下一层又是上一层的某个倍数。那么为了减少重复，可以推得，若第一层为X，那么第二层应为X的素数倍，第三层为第二层的素数倍……这样然后让第二层以后出现的FLAG打为1， 第一层遍历就可以跳过了。同时还设一个DP数组， 维护的是到达某个值的最大层数。 总之就是DFS出最大层数。时间复杂度不会算了……

2. DP 解法： O(n²)... 维护两个数组 prev[i]: 符合题意的subset的第i个数的前一个数的index， dp[i]: nums[:i+1] 的最长符合题意subset长度。那么就可以

    i: 1 -> len(nums)
    j: 0 -> i
    dp[i] = dp[j] + 1, prev[i] = j if not nums[j] % nums[i] and 1 + dp[j] > dp[i]