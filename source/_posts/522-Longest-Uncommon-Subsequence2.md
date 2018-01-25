---
title: 522. Longest Uncommon Subsequence2
date: 2018-01-10 15:50:03
tags: [string]
categories: leetcode
---

{% blockquote  leetcode https://leetcode.com/problems/longest-uncommon-subsequence-ii/description/ 522. Longest Uncommon Subsequence II %}
题目描述如下：

Given a list of strings, you need to find the longest uncommon subsequence among them. The longest uncommon subsequence is defined as the longest subsequence of one of these strings and this subsequence should not be any subsequence of the other strings.

A subsequence is a sequence that can be derived from one sequence by deleting some characters without changing the order of the remaining elements. Trivially, any string is a subsequence of itself and an empty string is a subsequence of any string.

The input will be a list of strings, and the output needs to be the length of the longest uncommon subsequence. If the longest uncommon subsequence doesn't exist, return -1.

Example 1:

    Input: "aba", "cdc", "eae"
    Output: 3

Note:
1. All the given strings' lengths will not exceed 10.
2. The length of the given list will be in the range of [2, 50].
{% endblockquote %}

---

## 解题思路：

1. 38赞， 207 差评。 但是我感觉题目并没那么差， 虽然题目有点投机取巧

2. 考验基本代码能力， WA 了10来次， 重写了一遍才过的， 对着OJ DEBUG…… 哎

3. 题目所求的最大长度 即是 某个字符串的长度。这个字符串需要满足的条件如下：
    - 唯一
    - 不是比它长的字符串的子序列
    - 最大