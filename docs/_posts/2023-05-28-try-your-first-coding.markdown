---
layout: post
title:  "Try your first coding"
categories: jekyll update
---
## 尝试编写你的首段程序

在《[什么是编程]》这篇教程的最后我们总结到：“程序 = ( 指令 + 数据 ) X 流程，而编程，就是使用计算机语言编写这样的程序的过程”。现在就让我们尝试编写第一段简单的程序吧~

### 编程环境介绍

通常，完全的编程新手鼓足勇气踏入程序世界的第一步就会碰到一个让人“入新手村而中道崩殂”的大障碍：搭建编程环境。新人即使对着保姆级的环境搭建教程和软件安装说明书，也很有可能因为自己的电脑环境与教程的演示环境有些许差别而碰上整日无法解决的问题。考虑到这一点，我们接下来将直接使用嵌入浏览器网页中的[Processing]编程环境来编程。如果想要用它编程，你只需要将代码写在如下所示的位置
```javascript
<script type="application/processing">
//你只需要将你的代码写在上面这行'<script type="application/processing">'和下面的'</script>'之间
//代码运行时，Processing环境会自动读入你写在这两行之间的所有代码，然后“理解”你的代码并执行
//比如下面这一行就是这一整段文本真正会被执行的代码

ellipse(50,50,15,15);

</script>
<canvas> </canvas>
```
马上在下面的编程环境里试试吧：

[codepen_embed height="342.6666564941406" default_tab="html,result" slug_hash="bGmjEwE" preview="true" editable="true" user="dreanlin"]See the Pen <a href="https://codepen.io/dreanlin/pen/bGmjEwE">
  ExamplePrintCalResult</a> by Dreanlin (<a href="https://codepen.io/dreanlin">@dreanlin</a>)
  on <a href="https://codepen.io">CodePen</a>.[/codepen_embed]


[什么是编程]:https://hwfdf
[Processing]:https://baike.baidu.com/item/Processing/378062