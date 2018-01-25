---
title: 209. Minimum Size Subarray Sum
date: 2018-01-19 20:38:52
tags: [Array ,Two Pointers, Binary Search]
categories: leetcode
---


{% blockquote  leetcode https://leetcode.com/problems/minimum-size-subarray-sum/description/ 209. Minimum Size Subarray Sum %}
题目描述如下：

Given an array of n positive integers and a positive integer s, find the minimal length of a contiguous subarray of which the sum ≥ s. If there isn't one, return 0 instead.

For example, given the array [2,3,1,2,4,3] and s = 7,
the subarray [4,3] has the minimal length under the problem constraint.

More practice:
If you have figured out the O(n) solution, try coding another solution of which the time complexity is O(n log n).

Credits:
Special thanks to @Freezen for adding this problem and creating all test cases.
{% endblockquote %}

---

## 解题思路：

1. 二分已G 。 一直把思路放在数组上 没想到二分的是窗口大小。 也就是 二分 窗口(1, len(array)) , 然后查找是否存在 对应的解 ， 如果存在 ， 变小， 如果不存在变大。 边界条件需要考虑。

2. 划窗。。。 遍历所有可能找最小。