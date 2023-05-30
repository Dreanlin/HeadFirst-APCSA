---
layout: post
title:  "Tutorial Description"
categories: jekyll update
---

## 本教程使用说明

### 教程创作目标

我编写这个博客教程的目标简单来说就是：希望通过教授 AP-CSA 考试范围内的 Java 语言编程概念来帮助读者入门编程。所以该系列取名为 **HeadFirst-APCSA** 也参照有名的计算机科学入门书系：HeadFirst 系列。  

### 教程内容

本教程的内容主要包括以下模块：
1. AP-CSA 考试涉及到的[Java编程语言]相关概念以及使用Java语言编写程序
   - 简单来说这个系列就是教 Java 编程的，但是因为 Java 语言从诞生至今经过了几十年的发展，语法规则非常庞大（即使是有经验的 Java 程序员也需要持续不断的学习新语法），并且我们的目标只是入门编程、学会用程序来解决问题，所以我们会选用[美国AP考试]的[计算机科学A]这门课的考纲作为大纲，学会了这个范围内的 Java 核心语法和概念就足以让我们在编程领域初窥门径，编写出能帮助自己的有用程序。
2. 使用[Processing创意编程]的入门介绍
   - 考虑到本系列的读者多是编程新手，并且本系列的主体内容是 Java 编程。而 Processing 将 Java 的语法简化并将其运算结果可视化，让初学者能很快享有声光兼备的交互式多媒体作品，所以它是一个理想的入门工具。我们会在本系列最开始通过 Processing 编程快速上手，然后过度到完全的 Java 编程。
3. 计算机科学基础概念和编程基础概念的入门科普
   - 虽然本教程主要关注 Java 编程内容，但是也会简单介绍一些诸如“计算机内部到底怎么做到这个”、“程序指令为啥就能操作计算机做到这个”之类的知识，不求高精尖，但求通俗易懂。（其实是能力有限讲不了太深奥、高精尖的东西）

### 目标读者

本教程主要内容涉及 AP-CSA 考试内容，所以参考 AP-CSA 对学生群体的先修要求，只需要读者具有高中一年级数学的知识，了解线性函数、函数组合的概念，以及能够使用平面直角坐标系来表示平面上的点。

### 编程语言选择

本教程系列中，我们学习 Java 语言的原因是：Java 语言足够成熟、Java 应用足够广泛、为了准备 AP-CSA 考试（考的就是 Java 编程）。但是我们为什么要选择在最开始的时候使用 Processing 语言呢？A long story···

在《[什么是编程]》这篇教程的最后，我们已经知道，程序就是使用编程语言，让计算机按照指定的流程（英文：flow），根据咱们代码里的指令（英文：instruction）和数据（英文：data）来完成任务。那么我们要能使用某种语言写码来操作计算机，首先我们肯定得知道：

1. 这个编程语言提供了哪些指令
2. 这些指令需要什么数据来执行

以上两点在使用不同的编程语言来写码的时候，是有区别的，比如《什么是编程》中我们举例用到的 C 语言程序：

```c
  STEP1: A = 0;
  STEP2: B = 2;
  STEP3:
  if(B == 0){
         goto STEP7;
         }
         else{
         goto STEP4;
         }
  STEP4: A = A + 3;
  STEP5: B = B - 1;
  STEP6: goto STEP3;
  STEP7: printf("%d", A);
  STEP8: return 0;
```

其中的 “goto” 指令，在现代的绝大多数高级编程语言（Processing、python）中都是没有的，每行代码最前面的 “STEPx: ” 在 Processing 中也是不支持的。  

另外即使是起同样作用的指令，我们调用时需要给它的数据、以及调用语法也是不一样的：  
比如同样是**打印**指令，在打印整数 *10* 的时候，C 语言是`print("%d", 10);`、Processing 是`print(10);`、而 Python 是`print(10)`。  
可以看到，C 语言的**打印**指令除了需要我们给它被打印的数字 *10* 以外，还需要一个参数 *"%d"* ，而 Python 和 Processing 都只需要整数 *10* 即可。并且对比 Processing 和 Python 的**打印**指令我们发现，即使是同一个指令并且打印的数字都一样，但是 Processing 语言是要求每个指令的结束必须用分号显性标记，而 Python 不需要。  

如果这些编程语言各自差距都这么大，





[Java编程语言]:https://www.runoob.com/java/java-intro.html
[美国AP考试]:https://baike.baidu.com/item/%E7%BE%8E%E5%9B%BD%E5%A4%A7%E5%AD%A6%E5%85%88%E4%BF%AE%E8%AF%BE%E7%A8%8B/59924783
[计算机科学A]:https://apcentral.collegeboard.org/media/pdf/ap-computer-science-a-course-overview.pdf
[Processing创意编程]:https://baike.baidu.com/item/Processing/378062
[什么是编程]:https://dreanlin.github.io/HeadFirst-APCSA/jekyll/update/2023/05/14/whats-programming.html