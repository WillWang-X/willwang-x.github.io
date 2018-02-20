--- 
layout: post
title: 重新发现核函数
tags:
- 机器学习 
status: publish
type: post
published: true
---

<br>

问题始于，我从在魔鬼那里学会了: [Kernel Trick](https://www.zhihu.com/question/21094489/answer/86273196)

## 1.数据升维
	
那如何实现呢？更精确地说：如何使数据升维呢？
	
从SVM我们知道了那个用来分类函数：
	
![hyper plane](https://i.imgur.com/ldvJFT8.png)
	
申明一下：我们升维的目的在于，SVM是一个线性分类器。所以它不能画一些弯弯曲曲的线。
	
那现在简单了：
	
只要把这个函数中 x 变成 f(x) 就行了。
	
直观看图：
	
![投射](https://i.imgur.com/C5f7dDg.gif)
	
## 2. 简化计算
	
这样就好了么？数据升维，我们是可以找到超平面了，但是也意味着我们计算量上升了。
	
来体会一下：
	
![数据升维点乘计算](https://i.imgur.com/zOkIYCc.jpg)
	
> 加入我们对一个二维空间做映射，选择的新空间是原始空间的所有一阶和二阶的组合，得到了五个维度；如果原始空间是三维，那么我们会得到 19 维的新空间，这个数目是呈爆炸性增长的。
	
那怎么办呢？
	
有高人指点：
	
> 数据升维的本质是找到一种映射关系，使得在高维空间能够刻画这些数据在低维空间的**分布**。
	
分布？简而言之，就是数据之间的关系，不管在什么空间，数据之间的关系都是相似的。
	
来来来，再看看，我们分类函数的特点: **Dot Product.**

有没有想起来什么？

嗯... 	


![dot product](https://i.imgur.com/51p3m4Y.png)
	
不，不是这个。是下面这个。
	
![kernel function example](https://i.imgur.com/woKyG9B.png)
	
两个数据升维Dot Product的过程了，可以用一个函数就刻画出来了。

是不是很激动！我不用到**高维**去做那个**复杂计算**了，我甚至不需要知道我投影到高维**空间长什么样**，我只需要找到**这个函数**去刻画这个「点乘」的投影过程，然后用**这个函数**去计算就可以啦！**大大的简化了计算量！**
	
再后来，人们把这个函数就**「kernel function」**! 
	
## 3. 想多玩一会？
	
- 两本书可以读一读: [《Learning with Kernels》](https://book.douban.com/subject/1763633/), [《Kernel Methods for Pattern Analysis》](https://book.douban.com/subject/1789537/)
- 那如何找到这个Kernel Function呢？呃，这个有点复杂。
	
## 4. 感谢
	
0. Credit to Master Zhao, Wen Zhong, Yue 	
1. [Statistical and causal approaches to machine learning](https://www.youtube.com/watch?time_continue=29&v=ek9jwRA2Jio) : 对机器学习的核心概念介绍的清晰明了。
2. [支持向量机: Kernel](http://blog.pluskid.org/?p=685) : 通熟易懂系列，且有公式推导。
3. [机器学习有很多关于核函数的说法，核函数的定义和作用是什么？ - 豆豆叶的回答 - 知乎](https://www.zhihu.com/question/24627666/answer/35507744) ：直觉认识到核函数的特点：只要你能把连续函数空间填满，那么原空间上不同的分布在这个map下都会变成不同的点。
4. [How Support Vector Machines work / How to open a black box](https://www.youtube.com/watch?v=-Z4aojJ-pdg) : 看过关于SVM最好的直觉表达
5. [Linear Regression and Kernel Methods](http://www.numerical-tours.com/matlab/ml_2_regression/) : 来手把手实践一下。
6. [How to intuitively explain what a kernel is?](https://stats.stackexchange.com/questions/152897/how-to-intuitively-explain-what-a-kernel-is) : 核函数的直观例子
7. [Kernel Functions for Machine Learning Applications](http://crsouza.com/2010/03/17/kernel-functions-for-machine-learning-applications/) : 核函数大全
8. [Vector Calculus: Understanding the Dot Product](https://betterexplained.com/articles/vector-calculus-understanding-the-dot-product/) : 内积的直观理解  

<br>
<br>

简之           
2018.02.19
