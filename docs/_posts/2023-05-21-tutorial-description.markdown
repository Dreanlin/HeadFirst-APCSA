---
layout: post
title:  "Tutorial Description"
categories: jekyll update
---

## 本教程使用说明

### 配套讲解视频

<iframe src="//player.bilibili.com/player.html?aid=571992282&bvid=BV1Zz4y1q7Gu&cid=1155017662&page=1" scrolling="no" border="0" frameborder="no" framespacing="0" allowfullscreen="true"> </iframe>

### 教程创作目标

我编写这个博客教程的目标简单来说就是：希望通过教授 AP-CSA 考试范围内的 Java 语言编程概念来帮助读者入门编程。所以该系列取名为 **HeadFirst-APCSA** 也参照有名的计算机科学入门书系：HeadFirst 系列。  

### 教程内容

本教程的内容主要包括以下模块：  

1. AP-CSA 考试涉及到的[Java编程语言]相关概念以及使用Java语言编写程序
   - 简单来说这个系列就是教 Java 编程的，但是因为 Java 语言从诞生至今经过了几十年的发展，语法规则非常庞大（即使是有经验的 Java 程序员也需要持续不断的学习新语法），并且我们的目标只是入门编程、学会用程序来解决问题，所以我们会选用[美国AP考试]的[计算机科学A]这门课的考纲作为大纲，学会了这个范围内的 Java 核心语法和概念就足以让我们在编程领域初窥门径，编写出能帮助自己的有用程序。
2. 使用[Processing创意编程]的入门介绍
   - 考虑到本系列的读者多是编程新手，并且本系列的主体内容是 Java 编程。而 Processing 将 Java 的语法简化并将其运算结果可视化，让初学者能很快享有声光兼备的交互式多媒体作品，所以它是一个理想的入门工具。我们会在本系列最开始通过 Processing 编程快速上手，然后过渡到完全的 Java 编程。
3. 计算机科学基础概念和编程基础概念的入门科普
   - 虽然本教程主要关注 Java 编程内容，但是也会简单介绍一些诸如“计算机内部到底怎么做到这个”、“程序指令为啥就能操作计算机做到这个”之类的知识，不求高精尖，但求通俗易懂。（其实是能力有限讲不了太深奥、高精尖的东西）

### 目标读者

本教程主要内容涉及 AP-CSA 考试内容，所以参考 AP-CSA 对学生群体的先修要求，只需要读者具有高中一年级数学的知识，了解线性函数、函数组合的概念，以及能够使用平面直角坐标系来表示平面上的点。

### 编程语言选择

本教程系列中，我们学习 Java 语言的原因是：Java 语言足够成熟、Java 应用足够广泛、为了准备 AP-CSA 考试（考的就是 Java 编程）。但是我们为什么要选择在最开始的时候使用 Processing 语言呢？  

在《[什么是编程]》中我们知道了几乎任何图灵完备的编程语言都是通用语言，只是每种语言各有所长。而Processing 语言的特点就在于它非常容易用来绘图、制作动画、声光效果，相比于 Java 它更生动；同时，它的语法几乎和 Java 一模一样但是更简单易懂，非常方便初学者入门又便于无缝衔接到 Java 学习，比如分别用 Java 和 Processing 打印 “Hello World”：

```java
//Java版
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello World");
    }
}
```

```java
//Processing版
println("Hello World");
```

做个离谱但是形象的比喻，可以将 Processing 和 Java 的关系简单地理解成说明文之类的作文文体（Processing）和中文语言（Java）的关系。直接学会熟练、随心使用中文比较难，先学最基本的中文语法然后在说明文的框架下写文章就简单很多，并且还可以拿着被说明的物件实实在在地理解文字、词汇的含义。


[Java编程语言]:https://www.runoob.com/java/java-intro.html
[美国AP考试]:https://baike.baidu.com/item/%E7%BE%8E%E5%9B%BD%E5%A4%A7%E5%AD%A6%E5%85%88%E4%BF%AE%E8%AF%BE%E7%A8%8B/59924783
[计算机科学A]:https://apcentral.collegeboard.org/media/pdf/ap-computer-science-a-course-overview.pdf
[Processing创意编程]:https://baike.baidu.com/item/Processing/378062
[什么是编程]:https://dreanlin.github.io/HeadFirst-APCSA/jekyll/update/2023/05/14/whats-programming.html