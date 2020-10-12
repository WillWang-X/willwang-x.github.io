--- 
layout: post
title:  什么是泛化？猜！
tags:
- tech
status: publish
type: post
published: true
---

<br>

> “If you can’t explain it simply, you don’t understand it well enough.” — Albert Einstein 
	
### 1. 问题这样子的：
	
```
给了一组数据: 1,2,4,7...	
下一个数是什么呢？


—— 某初二考试题
```
	
### 2. 想法是：
	
当时初二的我发现的规律是 `1+1=2`, `2+2=4`,`4+3=7`, 所以下一个就是`7+4=11`
	
但是如今的我可能会说答案不止一种：
	
可能是..
	
1,2,4,7,**12**,20 (规律是： `A(n+2) = A(n+1) + A(n) + 1`)
	
1,2,4,7,**14**,28 (28的除数)
	
...
甚至是你可能随便猜一个数字都对，0,1,2,4,5,7,8,9,11,12,13,14...
	
去[The on-line encyclopedia of integer sequences](https://oeis.org/search?q=1%2c2%2c4%2c7) 看一下发现他们都是有根据:
	
![0](https://i.imgur.com/yGckkJf.png)
	
![1](https://i.imgur.com/XHLItnF.png)
	
![2](https://i.imgur.com/MWi5NW2.png)

...
	
后来搞「机器学习」的大人们，把这个「**猜下一个**」的能力叫做「**Generalization**」. 我们还不知道实际情况是怎样子的，然后我们根据我们的规律`A(n+2) = A(n+1) + A(n) + 1`猜了下一个是`11`，发现实际情况对了，下一个就是`11`，问题我们得出规律就一定符合真实的情况么？
	
然后我们看到了这些...
	
![11-1](https://i.imgur.com/2T8q7x0.png)
	
![11-2](https://i.imgur.com/weO8ntM.png)
	
![11-3](https://i.imgur.com/A8oyUTS.png)

...
	
😂我们发现了符合下一个是`11`的情况，可能有**好多规律**都是满足的。搞机器学习的大人们把这些发现的「规律」叫做「Model」。所以当他们说训练的**模型泛化能力不行**的时候，他们就是可能遇到了上面的情况。
	
这时候他们想要干什么呢？可能要更多的数据。
	
下面这多数够么？
	
1, 2, 4, 7, 11, 16, 22, 29, 37, 46, 56, 67, 79, 92, 106, 121, 137, 154, 172...
	
发现下一个在[The on-line encyclopedia of integer sequences](https://oeis.org/search?q=1%2C+2%2C+4%2C+7%2C+11%2C+16%2C+22%2C+29%2C+37%2C+46%2C+56%2C+67%2C+79%2C+92%2C+106%2C+121%2C+137%2C+154%2C+172&sort=&language=&go=Search) 数据还是有4种规律，下一个可以是：191或190
	
至少我们发现给定数据越多，我们可以发现更精确的「模型」，那我们看一个**数据多少模型性能**的栗子：
	
![data-model](https://i.imgur.com/SqqoShr.png)
	
### 3. 小结一下
	
**数据的多少，决定了你模型泛化能力的上限。**	

### 4. 想多玩一会？
1. 当模型泛化能不行时，还有哪些原因？各自的特征是什么，如何解决？
2. 如何确定自己不是因为数据不够而模型性能不好？
3. 小数据样本有没有可能训练出泛化能力强的模型？如果可以，在什么情况下？

### 5. 感谢
	
1. [Statistical and causal approaches to machine learning](https://www.youtube.com/watch?time_continue=29&v=ek9jwRA2Jio)
1. [The on-line encyclopedia of integer sequences](https://oeis.org/)
	

<br>
<br>
           
2018.03.18          

