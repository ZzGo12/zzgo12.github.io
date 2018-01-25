---
title: 16. 3Sum Closest
date: 2018-01-21 17:17:05
tags: [Array,Two Pointers]
categories: leetcode
---

{% blockquote  leetcode https://leetcode.com/problems/3sum-closest/description/ 16. 3Sum Closest %}
题目描述如下：

Given an array S of n integers, find three integers in S such that the sum is closest to a given number, target. Return the sum of the three integers. You may assume that each input would have exactly one solution.


    For example, given array S = {-1 2 1 -4}, and target = 1.

    The sum that is closest to the target is 2. (-1 + 2 + 1 = 2).


{% endblockquote %}

---

## 解题思路：

这题o(n2)思路又一次阵亡...
目标函数是 f = |(x+y+z - target)|
然后 minimum(f) 就ok
首先sort s
遍历 s 中的每个数字 ， 对应索引 i.
令 j = i+1 , k = len(a) - 1
在满足 j < k 的情况下 根据算出的f 的大小 左右移动 j , k 。