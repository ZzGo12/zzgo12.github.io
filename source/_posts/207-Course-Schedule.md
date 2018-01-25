---
title: 207. Course Schedule
date: 2018-01-03 21:16:17
tags: [Depth-first Search,Breadth-first Search, Graph, Topological Sort]
categories: leetcode
---


{% blockquote  leetcode https://leetcode.com/problems/course-schedule/description/ 207. Course Schedule %}
题目描述如下：
There are a total of n courses you have to take, labeled from 0 to n - 1.

Some courses may have prerequisites, for example to take course 0 you have to first take course 1, which is expressed as a pair: [0,1]

Given the total number of courses and a list of prerequisite pairs, is it possible for you to finish all courses?

For example:

    2, [[1,0]]

There are a total of 2 courses to take. To take course 1 you should have finished course 0. So it is possible.

    2, [[1,0],[0,1]]

There are a total of 2 courses to take. To take course 1 you should have finished course 0, and to take course 0 you should also have finished course 1. So it is impossible.

Note:
1. The input prerequisites is a graph represented by a list of edges, not adjacency matrices. Read more about how a graph is represented.
2. You may assume that there are no duplicate edges in the input prerequisites.
{% endblockquote %}

---

## 解题思路：

1. 用领接表存图， 会快很多。 （领接表不一定要用链表）

        matrix = [[] for _ in range(numCourses)]
        pre = prerequisites
        for p in pre:
            matrix[p[0]].append(p[1])

2. 找是否存在某个子图存在重复的边。 （只写了DFS， 应该拓扑更快？） 利用一个visited数组，每个顶点初始化为0， 表示未遍历。 然后遍历顶点， 如果顶点是未遍历的， 就DFS， DFS返回是否存在重边。

    def dfs(x):
        if visited[x] == -1:
            return False
        if visited[x] == 1:
            return True
        visited[x] = -1
        for nx in matrix[x]:
            if not dfs(nx):
                return False
        visited[x] = 1
        return True