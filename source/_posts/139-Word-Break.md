---
title: 139. Word Break
date: 2018-01-31 16:43:09
tags: Dynamic Programming
categories: leetcode
---


{% blockquote  leetcode https://leetcode.com/problems/word-break/description/ 139. Word Break %}
题目描述如下：

Given a non-empty string s and a dictionary wordDict containing a list of non-empty words, determine if s can be segmented into a space-separated sequence of one or more dictionary words. You may assume the dictionary does not contain duplicate words.

For example, given
s = "leetcode",
dict = ["leet", "code"].

Return true because "leetcode" can be segmented as "leet code".

UPDATE (2017/1/4):
The wordDict parameter had been changed to a list of strings (instead of a set of strings). Please reload the code definition to get the latest changes.

{% endblockquote %}

---

## 解题思路：

刚开始的想法是 定义一个递归函数 f, 那么 f(s) 就可以得到问题能否解决的值
那么 另 i = [0,len(s)) 遍历， f(s) = f(s[0:i]) + f(s[i+1:]) 这样递归下去。
但是有一个问题就是...递归出口？
一拍脑袋的想了应该是当长度为1？
试一下 结果死循环了 ， 心烦看了答案。

思路就是固定一部分 ， 让另一部分递归
其实 如果 s 能被dict 中的元素组成， 那么 一定有s[k:] in dict.
那么递归其实可以简化为 i = [0,len(s)) 遍历， 如果 s[i:] in dict 那么 f(s) = f(s[:i])。。。
然后用DP写的话

    i 0->len(s)-1
    j 0->i-1
    if dp[j]:
        if s[j+1:] in dict:
            dp[i] = True
            break
