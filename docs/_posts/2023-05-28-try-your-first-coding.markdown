---
layout: post
title:  "Try your first coding"
categories: jekyll update
---
## 尝试编写你的首段程序

本篇教程我们一起学习用 Processing 语言编写第一段程序，试试吧~

### 编程环境介绍

通常，完全的编程新手鼓足勇气踏入程序世界的第一步就会碰到一个让人“入新手村而中道崩殂”的大障碍：搭建编程环境。新人即使对着保姆级的环境搭建教程和软件安装说明书，也很有可能因为自己的电脑环境与教程的演示环境有些许差别而碰上整日无法解决的问题。考虑到这一点，我们接下来将直接使用嵌入浏览器网页中的 [Processing] 编辑器（英文：editor）来编程。如果想要用它编程，你只需要将代码写在如下所示的位置

```javascript
<script type="application/processing">
//你只需要将你的代码写在上面这行'<script type="application/processing">'和下面的'</script>'之间
//代码运行时，Processing环境会自动读入你写在这两行之间的所有代码，然后“理解”你的代码并执行
//比如下面这一行就是这一整段文本真正会被执行的代码

ellipse(40,50,15,20);

</script>
<canvas> </canvas>
```

马上在下面的编程环境里试试吧：

<div class="codepen" data-height="342.6666564941406" data-default-tab="html,result" data-slug-hash="bGmjEwE" data-editable="true" data-user="dreanlin"  data-prefill='{"title":"TryYourFirstCoding","tags":[],"scripts":["https://cdnjs.cloudflare.com/ajax/libs/processing.js/1.6.0/processing.min.js"],"stylesheets":[]}'>
  <pre data-lang="html">&lt;script type="application/processing">
//像你正在读的我这几行中文讲解，是写在两个连续 / 符号右侧的“代码注释”
//Processing读入代码的时候会把“代码注释”直接无视
//这些注释单纯是我们写在代码里方便自己理解的提示信息
//你也可以按照需求在代码中写注释提示自己一些注意点
//现在你可以将上文中那行真正的代码 ellipse(40,50,15,20); 写在下面
//然后等待程序执行结束
//注意别忘了每行代码的最后，要用【英文分号】表示这行代码的结尾

&lt;/script>
&lt;canvas> &lt;/canvas></pre></div>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

### 指令和函数

我们已经知道，程序只是按照一定流程编排的指令+数据。前几篇教程中，我们看到的都是一些最简单的指令，比如加减乘除的运算，假设我们把 “+”、“-” 符号看成代码中的指令，把符号两侧的数看作数据，这也是符合我们最初的定义的。但是除了这些运算符，在 Processing 中还有一种更普遍的指令形式，就是**函数**（英文：function）。  

在上一部分我们看到的`ellipse(40,50,15,20);`就是一个函数，之所以叫“函数”，是因为它和我们所熟悉的数学中的函数表达式非常相像。比如我们定义一个一次函数：
$$f(x) = 2x + 1$$

我们知道$f$的含义是，它代表了一种法则：它需要你给他一个参数$x$，然后它会返回给你$2 \times x + 1$的值。在数学试卷上你想表示用这个函数来求某个值（比如 7）时，只需要写上$f(7)$大家就能明白你的意思是调用$2x+1$的法则来算出$x=7$时的结果。  

同样的，Processing 语言中的函数`ellipse`也代表了一种法则：只要你把参数（英文：parameter）写在紧跟着它的括号里，它就会用你给的参数来画出一个椭圆。那它画椭圆时是怎么用我们给的参数的？  

可以看到，前面我们调用它的时候在括号里给了它4个参数`(40,50,15,20)`，这4个参数按从左到右的顺序，含义分别是：  

- 椭圆中心的x轴坐标（本例中为40）
- 椭圆中心的y轴坐标（本例中为50）
- 椭圆的宽度（本例中为15）
- 椭圆的高度（本例中为20）

唯一需要注意的是，我们用 Processing 语言编程指定坐标时，告诉计算机的这个坐标（40，50），其坐标系原点是：在代码运行时，出现的这个灰色矩形画布（英文：canvas）的左上角的点。下面的图示展示了`ellipse(3,3,4,6);`这个函数调用时，画出的椭圆在坐标系中的示意（*[点此跳转至图片来源]*）。  
![坐标系中的椭圆]({{ "/reference/post-try_your_first_coding/EllipseInCoSystem.svg" | relative_url }})

### Processing中的绘图相关指令简介

了解了函数指令的含义，现在我们就来多学一些 Processing 语言里**可供直接调用**的、用于绘制简单图形的函数指令吧，想了解更全面的函数指令可以查阅 Processing 官网的[参考列表]：

1. `size(width,height);`表示设置一块宽为 width 高为 height 的画布（英文：canvas），且按照我们前文提到的，画布的左上角是整个坐标系的原点，之后绘制的图形只要没有超出画布范围（x 坐标不超过 width 值，y 坐标不超过 height 值）就可以正常显示在画布上。这个函数需要在所有其他的绘图函数之前调用，毕竟没有画布就没法画画了；但是如果你忘记调用这个 size 函数也不用惊慌，Processing 发现你没主动调用 size 函数就会自动在最开始先调用`size(100,100);`，要不然我们之前的那个直接调用`ellipse(40,50,15,20);`的例子也不可能画出椭圆来。
   - 参数width：设置画布的宽度
   - 参数height：设置画布的高度

2. `rect(a, b, c, d);`表示在画布上画出一个矩形
   - 参数a：矩形**左上角**的点的x轴坐标
   - 参数b：矩形**左上角**的点的y轴坐标
   - 参数c：矩形的宽度
   - 参数d：矩形的高度

3. `triangle(x1, y1, x2, y2, x3, y3);`表示在画布上画出一个三角形
   - 参数x1：第一个点的x轴坐标
   - 参数y1：第一个点的y轴坐标
   - 参数x2：第二个点的x轴坐标
   - 参数y2：第二个点的y轴坐标
   - 参数x3：第三个点的x轴坐标
   - 参数y3：第三个点的y轴坐标  

4. `fill(v1, v2, v3);`表示设置绘制图形时的填充色，只要调用这个函数，之后画出来的图形（比如上面提到的矩形和三角形）的填充色都会是你在这次调用中设定的颜色，颜色通过 v1、v2、v3三个值按照[RGB法则]设定（这三个参数的范围限定为0~255的整数）。
   - 参数v1：表示填充色的Red值
   - 参数v2：表示填充色的Green值
   - 参数v3：表示填充色的Blue值

现在就让我们用目前学习的这几个函数来绘制一些简单的图形吧：

<div class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="oNaMbLQ" data-editable="true" data-user="dreanlin"  data-prefill='{"title":"BasicShape","tags":[],"scripts":["https://cdnjs.cloudflare.com/ajax/libs/processing.js/1.6.0/processing.min.js"],"stylesheets":[]}'>
  <pre data-lang="html">&lt;script type="application/processing">

// 注意：之前提过，在Processing中两个斜杠符号后的本行内容是注释，不是程序的内容，我们可以随意编辑一些用来提示自己的内容
size(500,400);// 通过左边这个size函数调用，我们让Processing准备一块宽500，高400的画布

fill(133,0,133);// 通过左边这个fill函数调用，我们让Processing给接下来画的图形都用上RGB值为(133,0,133)的颜色，也就是紫色，你可以谷歌一下RGB颜色表来查找自己喜欢的颜色的RGB，然后调用fill函数画出这种填充色的图形
rect(20,20,50,40);// 通过左边这个rect函数调用，我们让Processing以(x=20,y=20)为左上角坐标点，画出一个宽50、高40的矩形；因为上一步我们用fill设置了填充色为紫色，现在这个矩形内部就是紫色的
triangle(80,80,120,80,100,120);// 通过左边这个triangle函数调用，我们让Processing在以(80,80)(120,80)(100,120)三个点为顶点画出一个三角形；因为我们上一次调用的fill函数设置的填充色是(133,0,133)所以现在三角形填充色还是紫色
fill(0,100,0);// 现在我们再次调用fill函数并且设置RGB值为(0,100,0)，这样接下来画的图形就是这个RGB值对应的绿色了
ellipse(200,200,100,80);// 通过左边这个ellipse函数调用，我们让Processing以点(x=200,y=200)为中心，画出了一个宽为100、高为80的椭圆；因为上一步我们调用了fill(0,100,0)，所以现在画出来的图形填充色都是绿色了

&lt;/script>
&lt;canvas> &lt;/canvas></pre></div>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

现在你已经知道了椭圆、圆（宽高一样的椭圆）、矩形、正方形（宽高一样的矩形）、三角形怎么绘制，也知道了怎么改变填充色，直接试试在上面这个环境中修改代码然后绘制自己喜欢的图形吧。如果还需要查询绘制其它更多图形的函数，可以去 Processing [参考列表]查询，比如画[线段]、画[弧形]等。

[Processing]:https://baike.baidu.com/item/Processing/378062
[点此跳转至图片来源]:https://processing.org/cd3baea53c123bf79e619a7c2b9afb2c/drawing-10.svg
[参考列表]:https://processing.org/reference
[线段]:https://processing.org/reference/line_.html
[弧形]:https://processing.org/reference/arc_.html