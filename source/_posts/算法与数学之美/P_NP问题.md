---
title: P/NP 问题
date: 2019-09-22
tags: [算法,数学]
id: 1
---

夜色降临，三男（老张、老王和老李）一女（小刘）三人对视而坐。

**老王率先打破僵局，说**：既然大家都还没吃饭，今晚我们叫麻辣烫怎么样？我来点。

**小刘**：可以哦，终于可以吃上王哥的麻辣烫了呀~

**老张**：下次我来。

**老李**：不如今天一起呗。

四人迅速点完，等待外卖小哥上门，期间有些无聊，老李趁机开启了话题。

**老李**：现在有些无聊，不如我们聊一聊 NP 咋样？嘿嘿嘿~

**小刘**：李哥你在说什么呀（脸色微微泛红）

**老王**：我知道，我先来说吧。所谓 NP 其实是计算复杂度理论中最重要的集合之一。非决定性多项式集合 ( non-deterministic polynomial )，简称 NP。

> 它包含 P 和 NP-complete。 P 集合的问题即在多项式时间内可以找出解的决策性问题 ( decision problem ) 集合。注意 NP 包含 P 和 NP-complete 问题, 因此 NP 集合中有简单的问题和不容易快速得到解的难题。

那么画图表示就是下面这样：
![](/resource/img/15691427327856.jpg)

**老张**：说的好，我来补充说一下 NP-complete 问题，又叫 NP 完备，简称 NPC，注意不是游戏里那个。
> NPC 是计算复杂度理论中，决定性问题的等级之一。NP 完备是 NP 与 NP 困难的交集，是 NP 中最难的决定性问题。因此 NP 完备问题应该是最不可能被化简为 P（多项式时间可决定）的决定性问题的集合。一个决定性问题C若是为NPC，则代表它对NP是完备的，这表示：
> 1. 它是一个NP问题。
> 2. 其他属于NP的问题都可在多项式时间内归约成它。
>
> 可归约在此意指对每个问题L，总有一个多项式时间多对一变换，即一个决定性的算法可以将实例l ∈ L转化成实例c ∈ C，并让c回答Yes当且仅当此答案对l也是Yes。为了证明某个NP问题A实际上是NPC问题，证明者必须找出一个已知的NPC问题可以变换成A。

但如果我们证明了一个问题是 NPC 问题，则表明这个问题很可能不能通过多项式时间解决。
![](/resource/img/15691427425317.jpg)

**老李**：得，一个回合下来都给你们说完了，那我就说说 NP-hard 问题吧。又称 NP 困难、NPH 问题。在说到 NPH 问题之前，你们也都对 P/NP 问题有一些了解了。
> P 问题就是在多项式时间内可以被解决的问题，NP 问题就是在多项式时间内可以被验证其正确性的问题。如果所有 NP 问题都可以多项式时间归约到某个问题，则称该问题为 NP 困难。因为 NP 困难问题未必可以在多项式时间内验证一个解的正确性（即不一定是 NP 问题），因此即使 NP 完全问题有多项式时间的解（P=NP），NP 困难问题依然可能没有多项式时间的解。因此 NP 困难问题“至少与 NP 完全问题一样难”。

说了这么多，小刘你一定很懵吧，看下面这个图的左半部分就可以很清楚的了解它们几个之间的关系了。
![](/resource/img/15691427520678.jpg)


**小刘**：几位哥，哦不，几位大佬，你们刚才说的我好多不懂的，比如说的什么，计算复杂度理论、多项式时间。。。

**老王**：哈哈哈，小刘还是很好学的吗。

> 计算复杂性理论（Computational complexity theory）是理论计算机科学和数学的一个分支，它致力于将可计算问题根据它们本身的复杂性分类，以及将这些类别联系起来。一个可计算问题被认为是一个原则上可以用计算机解决的问题，亦即这个问题可以用一系列机械的数学步骤解决，例如算法。
> 计算复杂性理论最成功的成果之一是NP完备理论。通过该理论，我们可以理解为什么在程序设计与生产实践中遇到的很多问题至今没有找到多项式算法。而该理论更为计算复杂性中的核心问题：P与NP的关系问题指明了方向。
> https://zh.wikipedia.org/wiki/計算複雜性理論

> 多项式时间（英语：Polynomial time）在计算复杂度理论中，指的是一个问题的计算时间 m(n) 不大于问题大小 n 的多项式倍数。任何抽象机器都拥有一复杂度类，此类包括可于此机器以多项式时间求解的问题。
> https://zh.wikipedia.org/wiki/多項式時間

常见的多项式时间有：

* 常量时间：O(1)
* 线性时间：O(n)
* 平方时间：O(n^2)
* 立方时间：O(n^3)
* O(n log(n))

与多项式时间对应的是超多项式时间，比如 指数时间 O(c^n)。

**小刘**：明白了，那我们点麻辣烫的等待时间应该是 O(log(n)) 时间了吧，也是属于多项式时间的。其实我们今天交流的 P/NP 问题指的是在计算复杂度上对于问题的复杂程度的一个划分。但是我注意到其中一个图中表达着 P = NP 和 P ≠ NP 的划分，那么 P ≠ NP  吗？

**老张**：哎呀，小刘真是聪明又细心，那么关于 P 等不等于 NP 这个问题也有得说了....

**哐哐哐有人敲门，不一会儿，只见老王拿着东西走了过来**：饭来喽，先吃麻辣烫，吃完我们再交流。

**老李**：对的，对的，吃完了我们可以深入交流一下嘛，哈哈。


PS：本文背景纯属虚构，内容均来自维基百科 https://zh.wikipedia.org/wiki/P/NP问题



