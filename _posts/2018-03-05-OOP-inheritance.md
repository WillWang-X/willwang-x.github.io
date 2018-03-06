--- 
layout: post
title:  面向对象之继承
tags:
- 概念集
status: publish
type: post
published: true
---

<br>

> 计算机软件开发的核心有二：程序的组织(面向对象技术)、问题求解(算法)。——— 《编程导论》

## 1. 问题是这样子的：
	
在学习JavaScript，发现了其继承机制设计有点特别，那Class-based 和 Prototype-based inheritance 有什么区别呢？
	
## 2. 三个故事
	
故事一：雅虎做了一个用Lisp写成的在线商店的案例，在他(Paul Graham)离开后，雅虎根本没法维护他写的代码，因为数万行Lisp没人能弄得很清楚。 —— 《黑客与画家》
	
故事二：1995年Sun公司将Oak语言改名为Java，正式向市场推出，打出广告：Write Once, Run Anywhere。其外，Java的模块化让大企业看到了曙光。这样一个程序员离职，一个新小伙子能迅速替补，完成之前的任务。开出一个程序员的成本，和代码维护的成本大大降低，于是大公司们纷纷力推。
	
故事三：1995年，“Java粉丝”的网景公司打算自己设计未来的网页脚本语言，要求必须"看上去与Java足够相似"，但是比Java简单，使得非专业的网页作者也能很快上手。但是，对Java不感兴趣而热衷于函数式编程的Brendan Eich, 收到公司的安排，10天时间就把Javascript设计出来了。他的设计思路是：（1）借鉴C语言的基本语法；（2）借鉴Java语言的数据类型和内存管理；（3）借鉴Scheme语言，将函数提升到"第一等公民"（first class）的地位；（4）借鉴Self语言，使用基于原型（prototype）的继承机制。
	
故事一是解释了为什么了面向对象编程方法会盛行？

故事二解释了为什么Java会盛行？

故事三解释了为什么JavaScript遭人吐槽的根源？
	
## 3. 继承对比
	
再来对比一下Java和JavaScript继承方式。
	
Java继承是自上而下，一层一层的叠加，而JavaScript是自下而上，一层一层的回溯。虽然共同的目标都是为了代码复用。但是Java的初衷就是要抢下大企业用户，帮助他们维护庞大的代码量，所以从父类开始，往下继承。而JavaScript的初衷就只是当一个网页的脚步语言，实现简单的交互功能，所以面向对象设计时，想着这个对象缺什么功能，就在它原型添加就好了，简单一点就好，即从需求出发，往上修改。所以，Java里面有**父类**和**子类**的概念，而JavaScript里面是**对象**和**原型**的概念。如果Java和JavaScript有性格的话，Java更稳重，而JavaScript更随性。[这具体意味这什么呢？](http://aaditmshah.github.io/why-prototypal-inheritance-matters/)
	
![Java VS JavaScript](https://i.imgur.com/ANJwcpy.png)
	
## 4. Show me the code 
	
下面对比一下Java和JavaScript在继承时是如何做的，以及如何Override的。

<script src="https://gist.github.com/WillWang-X/91af8fc596e450afd006045671d07676.js"></script>
	
	
<script src="https://gist.github.com/WillWang-X/a3791dac74fd738e94d025c80699a47e.js"></script>
	

## 5. 想多玩一会？
	
[为什么说Composition over Inheritance？](https://www.youtube.com/watch?v=wfMtDGfHWpA)
	
那Prototypal Inheritance好在哪里呢？: 来看看[Why Prototypal Inheritance Matters](http://aaditmshah.github.io/why-prototypal-inheritance-matters/)
	
## 5. 感谢
1. Master Zhao
1. [Master the JavaScript Interview: What’s the Difference Between Class & Prototypal Inheritance?](https://medium.com/javascript-scene/master-the-javascript-interview-what-s-the-difference-between-class-prototypal-inheritance-e4cd0a7562e9)
1. JavaScript: The Good Parts 
1. [Simple Inheritance with JavaScript](https://www.sitepoint.com/simple-inheritance-javascript/)
1. [Java - Inheritance](https://www.tutorialspoint.com/java/java_inheritance.htm)
1. [Javascript诞生记](http://www.ruanyifeng.com/blog/2011/06/birth_of_javascript.html)
1. [Javascript继承机制的设计思想](https://dancon.gitbooks.io/git-books/content/js/essay/JavaScript_OO_design.html)
1. [Scala 是一门怎样的语言，具有哪些优缺点？ - 紫杉的回答 - 知乎](https://www.zhihu.com/question/19748408/answer/62527490)
1. [跳出面向对象思想(一) 继承](https://casatwy.com/tiao-chu-mian-xiang-dui-xiang-si-xiang-yi-ji-cheng.html)
1. [如何继承 Date 对象？由一道题彻底弄懂 JS 继承](http://web.jobbole.com/93850/?utm_source=blog.jobbole.com&utm_medium=relatedPosts)
1. [JavaScript Prototype in Plain Language](http://javascriptissexy.com/javascript-prototype-in-plain-detailed-language/)
1. [Javascript继承机制的设计思想](http://www.ruanyifeng.com/blog/2011/06/designing_ideas_of_inheritance_mechanism_in_javascript.html)	

<br>
<br>

简之           
2018.03.05
