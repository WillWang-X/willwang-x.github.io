--- 
layout: post
title: 双指针之追逐
tags:
- 训练有素
status: publish
type: post
published: true
---

<br>

> You cannot pursue all your goals simultaneously or satisfy all your desires at once. ——— 《No, You Can’t Have It All》 	
	
![追逐](https://i.imgur.com/pWFuBCj.png)
	
### 1. 问题是这样子：
	
Given a string S and a string T, find **the minimum window** in S which will contain all the characters in T in complexity O(n).
	
For example,
	
S = "ADOBECODEBANC"
	
T = "ABC"
	
Minimum window is "BANC".
	
—— 《76. Minimum Window Substring》
	
### 2. 一个理想的思路是：
	
1. 求一个范围立马想到双指针：一个指头，一个指尾。
2. 先找满足条件的一个解，然后在走的过程，不断用限制条件看看能不能得到更好的解。
	
<center>😇</center>
	
<center>再升华一下，这个策略: </center>
	
<center>在LinkedList中，就是<b>快慢指针</b>，在ArrayList中，就是<b>移动窗口</b>。</center>
	
<center>  在生活中，就是<b>骑驴找马</b>。 🦄  </center>
<center> <b> (maintain a job while looking for a better one)
  </b> </center>

	
	
### 3. Show me the code 
	
<script src="https://gist.github.com/WillWang-X/bdfa9f90967f956d4cbb7773110c1c5b.js"></script>
	
### 4. 想再多玩一会？
	
1. [3. Longest Substring Without Repeating Characters](https://leetcode.com/problems/longest-substring-without-repeating-characters/description/)	
1. [19. Remove Nth Node From End of List](https://leetcode.com/problems/remove-nth-node-from-end-of-list/description/) : 快慢指针
1. [26. Remove Duplicates from Sorted Array](https://leetcode.com/problems/remove-duplicates-from-sorted-array/description/)
1. [209. Minimum Size Subarray Sum](https://leetcode.com/problems/minimum-size-subarray-sum/description/)
1. [487. Max Consecutive Ones II](https://leetcode.com/problems/max-consecutive-ones-ii/description/)
1. [567. Permutation in String](https://leetcode.com/problems/permutation-in-string/description/)
	
### 5. 感谢
	
[Coding Interviews and Snake (the game) Have This One Thing in Common](https://blog.pramp.com/coding-interviews-and-the-snake-game-have-this-one-thing-in-common-e0189fba1c9c)
	

<br>
<br>

简之           
2018.03.01
