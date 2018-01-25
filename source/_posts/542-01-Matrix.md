---
title: 542. 01 Matrix
date: 2018-01-03 21:16:17
tags: [Depth-first Search, Breadth-first Search, Dynamic Programming]
categories: leetcode
---


{% blockquote  leetcode https://leetcode.com/problems/01-matrix/description/ 542. 01 Matrix %}
题目描述如下：
Given a matrix consists of 0 and 1, find the distance of the nearest 0 for each cell.

The distance between two adjacent cells is 1.

Example 1:

Input:

    0 0 0
    0 1 0
    0 0 0

Output:

    0 0 0
    0 1 0
    0 0 0

Example 2:
Input:

    0 0 0
    0 1 0
    1 1 1

Output:

    0 0 0
    0 1 0
    1 2 1

Note:
1. The number of elements of the given matrix will not exceed 10,000.
2. There are at least one 0 in the given matrix.
3. The cells are adjacent in only four directions: up, down, left and right.
{% endblockquote %}

---

## 解题思路：

1. DFS加BFS一直T， 看了题解， 感觉过了的DFS是针对会T的样例改进的……，普通DFS貌似过不了，估计是时间卡的严。 BFS确实能过， 自己太菜。大概思路：将MATRIX中非0元素初始化为INF， 然后初始队列状态为所有的0点， 然后取出队首， 查看其四周元素， 如果能够使得其与0距离变小， 才将其加入队列。

2. DP 解法： 抄的别人。
For this question, we only need to consider 4 direction, up, down ,left and right.
so, first, I go through this matrix from top-left to down-right, and we can find the minimum distance from up and left, then, go through the matrix from down-right to top-left, so we can find the minimum distance from down and right. and it said the elements will not exceed 10,000, so I just set the initial value as 10,000.