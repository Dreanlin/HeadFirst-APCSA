---
layout: post
title:  "Whats Programming?"
categories: jekyll update
---
### 什么是编程？  

狭义地来说，编程暨编写程序，就是你按照某种 *计算机程序语言（Java、Python、Processing等）* 的语法规则，编写一段 *程序*，这段程序作为 *命令*，指挥计算机替你完成某项任务。  

比如在Processing中，我们直接输入如下代码，就可以让计算机 *计算* 并 *打印(print)* 我们想要的
    <math xmlns="http://www.w3.org/1998/Math/MathML" display="inline">
    <semantics>
      <mrow>
        <mn>123</mn>
        <mo>×</mo>
        <mn>456</mn>
      </mrow>
    </semantics>
    </math>
的结果（[点击此处查看结果]）：  
{% highlight java %}
   size(200, 300);

   //draw green stem
   strokeWeight(10);
   stroke(0, 128, 0);
   line(100, 100, 100, 300);

   //leafs
   ellipse(105, 200, 10, 10);
   ellipse(95, 225, 10, 10);

   //change stroke back to thin black line
   strokeWeight(1);
   stroke(0);

   //draw petals
   fill(255, 100, 0);
   ellipse(50, 50, 100, 100);
   ellipse(150, 50, 100, 100);
   ellipse(50, 150, 100, 100);
   ellipse(150, 150, 100, 100);

   //draw middle part
   fill(255, 128, 0);
   ellipse(100, 100, 100, 100);
//这段代码含义暂时不理解也没事，马上我们就会讲到
{% endhighlight %}

广义的来说，使用各种各样的*软件*，你通过各种不同的*操作*，使用计算机完成某些任务的过程，都可以看作编程。只是这个过程中，你使用的“计算机程序语言”是你使用这个软件时执行的一些  

自然地，我们会好奇，人怎么能和计算机这种机器进行沟通？我们通过文字字符(如：字母、数字)编写的近似人类自然语言的程序怎么会被用电驱动的硅基生物理解？既然聊到这了，我们不妨就用拟人和形象的方式来介绍一下这个问题：  

[点击此处查看结果]:{{ "/reference/Example-Print-PJS.html" | relative_url }}
