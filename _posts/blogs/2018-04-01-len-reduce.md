--- 
layout: post
title: 惊喜和规律
tags:
- tech
status: publish
type: post
published: true
---

<br>

> 好的艺术是制造惊喜，好的工程则最好不要。 —— 简之

# 1

在用Python的过程，有两个小问题困扰过我：

一个是用的顺手，想问问设计的人："Why Python has a len() function instead of a .length or .size property or method on the object?" 

一个是看的不顺眼，想问问写的人:“为什么不写稍微长一点点的代码可以让瞬间理解，而非要写更短的，像reduce()这样不能迅速Get到的代码，设计者是如何想的？”

# 2

后来发现Python的发明者Guido对这个两个问题都解释过。

### len()的诞生源于易读 

[Why do we need len()?](https://softwareengineering.stackexchange.com/questions/231387/python-methods-vs-builtin-functions)
> First of all, I chose len(x) over x.len() for HCI reasons (def __len__() came much later). There are two intertwined reasons actually, both HCI:
>
>
(a) For some operations, prefix notation just reads better than postfix — prefix (and infix!) operations have a long tradition in mathematics which likes notations where the visuals help the mathematician thinking about a problem. Compare the easy with which we rewrite a formula like x*(a+b) into x*a + x*b to the clumsiness of doing the same thing using a raw OO notation.
>
>
(b) When I read code that says len(x) I know that it is asking for the length of something. This tells me two things: the result is an integer, and the argument is some kind of container. To the contrary, when I read x.len(), I have to already know that x is some kind of container implementing an interface or inheriting from a class that has a standard len(). Witness the confusion we occasionally have when a class that is not implementing a mapping has a get() or keys() method, or something that isn’t a file has a write() method.
Saying the same thing in another way, I see ‘len‘ as a built-in operation. I’d hate to lose that. /…/

### reduce的死亡源于不易读 
[What is the problem with reduce()?](https://stackoverflow.com/questions/181543/what-is-the-problem-with-reduce)

> So now reduce(). This is actually the one I've always hated most, because, apart from a few examples involving + or *, almost every time I see a reduce() call with a non-trivial function argument, I need to grab pen and paper to diagram what's actually being fed into that function before I understand what the reduce() is supposed to do. So in my mind, the applicability of reduce() is pretty much limited to associative operators, and in all other cases it's better to write out the accumulation loop explicitly.
> 
Quick, what's the following code doing?
>
```
total = reduce(lambda a, b: (0, a[1] + b[1]), items)[1]
```
>
You can figure it out, but it takes time to disentangle the expression to figure out what's going on. Using a short nested def statements makes things a little bit better:
>
```
def combine (a, b):
return 0, a[1] + b[1]
total = reduce(combine, items)[1]
```
>
But it would be best of all if I had simply used a for loop:
>
```
total = 0
for a, b in items:
total += b
```
>
Or the sum() built-in and a generator expression:
>
```
total = sum(b for a,b in items)
```
>
Many uses of reduce() are clearer when written as for loops.

# 3

这增与删背后隐藏的设计思想是普世的。很多人都总结过，不过简而言之，四个字:「可预判性」。就是你拿到就知道如何使用，你看到就知道是什么。

艺术讲究的是启发，所以要让人惊喜，让你反思；而工程追求是效率，所以要可预判，减少错误，持续增长。

而关于效率，不是更短的实现，就是更好的实现。len()的短让人易读，感到美；而reduce的短，却让花更多时间去理解。

在 Zen of Python 写道：In the face of ambiguity, refuse the temptation to guess. There should be one -- and preferably only one -- obvious way to do it.




<br>
<br>
         
2018.04.01         

