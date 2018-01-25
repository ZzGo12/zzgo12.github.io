---
title: 187. Repeated DNA Sequences
date: 2018-01-03 21:16:17
tags: [Hash Table]
categories: leetcode
---


{% blockquote  leetcode https://leetcode.com/problems/repeated-dna-sequences/description/ 187. Repeated DNA Sequences %}
题目描述如下：
All DNA is composed of a series of nucleotides abbreviated as A, C, G, and T, for example: "ACGAATTCCG". When studying DNA, it is sometimes useful to identify repeated sequences within the DNA.

Write a function to find all the 10-letter-long sequences (substrings) that occur more than once in a DNA molecule.

Example 1:

    Given s = "AAAAACCCCCAAAAACCCCCCAAAAAGGGTTT",

    Return:
    ["AAAAACCCCC", "CCCCCAAAAA"].


{% endblockquote %}

---

## 解题思路：

很特别的一题。 因为是连续子串， 可以通过划窗生成。 然后通过HASH得到是否满足题意