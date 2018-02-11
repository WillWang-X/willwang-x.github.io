--- 
layout: post
title:  思路的诞生之正反思维：始末
tags:
- 思路的诞生
status: publish
type: post
published: true
---
	
> 凡事反过来想一想。 —— 不知名的观众	

### 一个理想的思路过程是：
	
1) 看到题目确定是一个**搜索**问题。
	
2）然后搜索问题的解法，想到有三种方法： **DFS，BFS，双端BFS**。
	
3）尝试完好写的BFS：超时！尝试完更好写的DFS: 超时！无计可施？
	
4) 双端BFS？... 念口诀：**正的不行，反的行。**
	
**Aha! 什么是树呢？**
	
众人疑惑脸。🤔
	
树的性质：**每一个非根节点有且只有一个父节点！** 
	
来，看图:
	
![Reaching Points](https://i.imgur.com/FsKaX4b.png)
	
所以我们可以通过“用大数减小数”来达到父亲节点！
	
快要到达了终点了... 但还是超时！
体会一下这个Edge case:（1，10**9）
	
那如何优化呢？

**Aha！GCD:Euclidean algorithm！
**	
### Show me the code
	
<script src="https://gist.github.com/WillWang-X/807067fb94a4f0ee03a5dd391b305d4b.js"></script>
2018.2.10

###  想多玩一些？

- [782. Transform to Chessboard
](https://leetcode.com/problems/transform-to-chessboard/description/) : 如何从结局推开始，让复杂问题变成一个简单问题？



简之