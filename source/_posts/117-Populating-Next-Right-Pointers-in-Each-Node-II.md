---
title: 117. Populating Next Right Pointers in Each Node II
date: 2018-01-02 19:32:01
tags: [Tree,Depth-first-Search]

categories: leetcode
---

{% blockquote  leetcode https://leetcode.com/problems/populating-next-right-pointers-in-each-node-ii/description/ 117. Populating Next Right Pointers in Each Node II %}
题目描述如下：
Follow up for problem "Populating Next Right Pointers in Each Node".

What if the given tree could be any binary tree? Would your previous solution still work?

Note:

You may only use constant extra space.
For example,
Given the following binary tree,

         1
       /  \
      2    3
     / \    \
    4   5    7

After calling your function, the tree should look like:

         1 -> NULL
       /  \
      2 -> 3 -> NULL
     / \    \
    4-> 5 -> 7 -> NULL


{% endblockquote %}

---

## 解题思路：

* prev(下一层的前向指针)
* current(当前指针)
* head(下一层的最左指针)

通过这三个指针的配合使用，模拟层次遍历...
从顶点node开始让每个node的prev->左孩子, 然后左孩子->右孩子....
暂时没看到dfs的做法，虽然标签是dfs， 一开始想了半天DFS未果 菜。