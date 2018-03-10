---
title: 775. Global and Local Inversions
date: 2018-03-04 11:24:31
tags: [Array,Math]
categories: leetcode
---

{% blockquote  leetcode https://leetcode.com/problems/global-and-local-inversions/description/ 775. Global and Local Inversions %}
题目描述如下：

We have some permutation A of [0, 1, ..., N - 1], where N is the length of A.

The number of (global) inversions is the number of i < j with 0 <= i < j < N and A[i] > A[j].

The number of local inversions is the number of i with 0 <= i < N and A[i] > A[i+1].

Return true if and only if the number of global inversions is equal to the number of local inversions.

Example 1:

    Input: A = [1,0,2]
    Output: true
    Explanation: There is 1 global inversion, and 1 local inversion.

Example 2:

    Input: A = [1,2,0]
    Output: false
    Explanation: There are 2 global inversions, and 1 local inversion.

Note:
- A will be a permutation of [0, 1, ..., A.length - 1].
- A will have length in range [1, 5000].
- The time limit for this problem has been reduced.

{% endblockquote %}

---

## 解题思路：

第一想法 分别求出global(逆序数) local ， 然后比较是否相等。 费时费力

然后偷看答案区标题写的是o(n) ... 觉得应该是有技巧的

写了个样例发现... 只要两个数字不是相邻， 并且存在逆序关系， 一定return False

所以问题变成判定是否存在非相邻数之间存在逆序关系

想了一会儿又没头绪 （ 数组里的元素从 0 ~ n-1 一直想不到干嘛用）

偷看答案

问题等价于 每个数 是否在其原有位置 或左或右……