---
title: 713. Subarray Product Less Than K
date: 2018-01-19 21:16:17
tags: [Array,Two Pointers]
categories: leetcode
---


{% blockquote  leetcode https://leetcode.com/problems/subarray-product-less-than-k/description/ 713. Subarray Product Less Than K %}
题目描述如下：
Your are given an array of positive integers nums.

Count and print the number of (contiguous) subarrays where the product of all the elements in the subarray is less than k.

Example 1:

    Input: nums = [10, 5, 2, 6], k = 100
    Output: 8
    Explanation: The 8 subarrays that have product less than 100 are: [10], [5], [2], [6], [10, 5], [5, 2], [2, 6], [5, 2, 6].
    Note that [10, 5, 2] is not included as the product of 100 is not strictly less than k.

Note:
- 0 < nums.length <= 50000.
- 0 < nums[i] < 1000.
- 0 <= k < 10^6.

{% endblockquote %}

---

## 解题思路：

类似的求连续子区间的题目， 通用的思路都是： 求以每一个数结尾的 满足题意的 个数有多少， 累加得到答案。
具体做法就是划窗找到满足题意的最大区间，算一下个数 然后再划。。。。 一直划到最后
P.S 这种题目我会习惯求出所有的区间，然后想办法通过并交之类的方法来求解。。。非常错误！