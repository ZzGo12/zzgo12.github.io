---
title: 678. Valid Parenthesis String
date: 2018-03-05 23:27:21
tags: String
categories: leetcode
---

{% blockquote  leetcode https://leetcode.com/problems/valid-parenthesis-string/description/ 678. Valid Parenthesis String %}
题目描述如下：

Given a string containing only three types of characters: '(', ')' and '*', write a function to check whether this string is valid. We define the validity of a string by these rules:


1. Any left parenthesis '(' must have a corresponding right parenthesis ')'.
2. Any right parenthesis ')' must have a corresponding left parenthesis '('.
3. Left parenthesis '(' must go before the corresponding right parenthesis ')'.
4. '*' could be treated as a single right parenthesis ')' or a single left parenthesis '(' or an empty string.
5. An empty string is also valid.

Example 1:

    Input: "()"
    Output: True

Example 2:

    Input: "(*)"
    Output: True

Example 3:

    Input: "(*))"
    Output: True

Note:
1. The string size will be in the range [1, 100].
{% endblockquote %}

---

## 解题思路：

GG

1. 前向遍历和后向遍历。 第一遍遍历 保证左括号 + * >= 右括号 第二遍遍历 保证右括号 + * >= 左括号 如果两个都成立， 就满足。

2. 一次遍历， 左括号+1 右括号-1 * 枚举出 三种可能 -1,0,1 ， 那么只要得到所有的可能取值， 最后这个集合中包含0 就OK。（过程中 若是存在整个集合小于0 直接淘汰）
