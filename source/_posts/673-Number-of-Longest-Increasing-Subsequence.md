---
title: 673. Number of Longest Increasing Subsequence
date: 2018-01-21 17:17:33
tags: Dynamic Programming
categories: leetcode
---

{% blockquote  leetcode https://leetcode.com/problems/number-of-longest-increasing-subsequence/description/ 673. Number of Longest Increasing Subsequence %}
题目描述如下：

Given an unsorted array of integers, find the number of longest increasing subsequence.

Example 1:

    Input: [1,3,5,4,7]
    Output: 2
    Explanation: The two longest increasing subsequence are [1, 3, 4, 7] and [1, 3, 5, 7].

Example 2:

    Input: [2,2,2,2,2]
    Output: 5
    Explanation: The length of longest continuous increasing subsequence is 1, and there are 5 subsequences' length is 1, so output 5.

Note: Length of the given array will be not exceed 2000 and the answer is guaranteed to be fit in 32-bit signed int.
{% endblockquote %}

---

## 解题思路：

求 最长上升子序列是老DP 了。。。。 然后写完定睛看了一眼题。。。 原来是求个数
其实就是加了个路径记录
dp 存 每个位置最长长度
cnt 存 每个位置对应最长位置有几条路径。
结果就是 最大长度 对应 cnt 的和

DP 代码：

    for i in range(1, len(nums)):
                maxi = nums[i]
                t = 0
                tt = 0
                for j in range(i):
                    if nums[j] < maxi:
                        t = max(t, dp[j])
                for j in range(i):
                    # print(i,j,dp[j],t)
                    if t == dp[j] and nums[j] < maxi:
                        tt += cnt[j]
                dp[i] = t + 1
                if tt:
                    cnt[i] = tt