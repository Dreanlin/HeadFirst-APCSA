---
layout: post
title:  "Whats Programming?"
categories: jekyll update
---

### 什么是编程？
编程，自然就是编写程序。那么随之而来又出现了一个问题，程序又是什么呢？  
我猜，提到程序是什么，你多半脑海里可能会有诸如以下片段的代码（[点此可以查看以下代码的实际效果]）：  
{% highlight java %}
void setup() {
  size(1000, 500); 
  noStroke();
  rectMode(CENTER);
}

void draw() {
  background(51); 
  fill(255, 204);
  rect(mouseX, height/2, mouseY/2+10, mouseY/2+10);
  fill(255, 204);
  int inverseX = width-mouseX;
  int inverseY = height-mouseY;
  rect(inverseX, height/2, (inverseY/2)+10, (inverseY/2)+10);
}
{% endhighlight %}  
狭义来说程序确实是代码，也就是我们编程时写下的一行行文本；广义地、从本质上来说，程序就是软件，它是我们用来指示计算机硬件（CPU等）执行某个任务而制作的产物。  
想象一下在非计算机领域的语境下我们提到“程序”时一般会怎么说？我们会说“要完成这个事情需要经过这么一个**程序**（或者**过程/步骤**），第一步...第二步...”。在计算机领域也是如此，把计算机想象成一个只能执行一些*固定功能*（比如：加减乘除、判断是或否）的机器人，此时你要指挥它完成一项工作，你必须考虑到它能做的这些*固定功能*，然后明确地告诉它用怎么样的**步骤**来执行它会的这些基本操作，从而完成这个复杂工作。  

想象一个非常简单的实例：
你现在有一个非常简陋的计算机（或者机器人），它的几个*固定功能*包括：
- 它会按你给的指令的顺序一步一步向下执行，除非你的指令内容明确让它去执行别的某一步、或者明确让它结束执行
- 它没有记忆力，但是它可以把你指定的某个黑板上的数字打印出来
- 你可以给它几块黑板，它可以在上面写下数字、修改数字、读出上面的数字（但是每个黑板只能记录一个整数，每次修改数字的时候它就把本来记在上面的整数擦掉然后写上一个新整数）
- 它会加法和减法，并且每次计算完后可以在你指定的黑板上记下加减法计算的结果
- 它会判断数字的大小

在这种情况下，如果你需要指挥它完成
         <math xmlns="http://www.w3.org/1998/Math/MathML" display="inline">
            <semantics>
              <mrow>
                <mn>3</mn>
                <mo>×</mo>
                <mn>2</mn>
              </mrow>
            </semantics>
         </math>
的计算，你要怎么指挥它？以下是一串可以做到这个任务的**程序**（仅使用上面提到的它的*固定功能*），虽然很呆板，但是方便我们之后继续解释程序的概念：  
```
1. 在 **黑板A** 上写下 **0**
2. 在 **黑板B** 上写下 **2**
3. 判断 **黑板B** 上的数字，如果等于 **0** 就执行**第7步**命令；否则执行**第4步**命令
4. 计算 **黑板A** 上的数字加上 **3** 后的结果，再把 **黑板A** 上的数字修改成计算的结果
5. 计算 **黑板B** 上的数字减去 **1** 后的结果，再把 **黑板B** 上的数字修改成计算的结果
6. 回到第3步执行
7. 打印出 **黑板A** 上的数字
8. 结束执行
```
现在你可以把自己当作计算机，用我准备的这两块“黑板”执行上面这一串命令：  
<label for="fname">黑板A:</label>
<input type="text" id="fname" name="fname">
<label for="lname">黑板B:</label>
<input type="text" id="lname" name="lname"><br>

如果我们仔细观察上面的这段程序，虽然它是一段自然语言，但是它的结构非常固定，比如：
- “在 **某黑板** 上写下 **某个数**”
- “计算 **某黑板** 上的数字**加/减** 去 **某数字** 的结果”

那么我们是否可以总结这个固定结构的规律，定义一个规则将上述程序“翻译”成更简单的固定结构文本呢？当然可以：
|程序的命令原文|翻译后的命令文本|翻译规则|
|--|--|--|
|"1. 在 **黑板A** 上写下 **0**"|STEP1: A = 0;||
|"2. 在 **黑板B** 上写下 **2**"|STEP2: B = 2;||
|"3. 判断 **黑板B** 上的数字，如果等于 **0** 就执行**第7步**命令；否则执行**第4步**命令"|STEP3:<br>if(B == 0){<br>goto STEP7;<br>}<br>else{<br>goto STEP4;<br>}||
|"4. 计算 **黑板A** 上的数字加上 **3** 后的结果，再把 **黑板A** 上的数字修改成计算的结果"|STEP4: A = A + 3;||
|"5. 计算 **黑板B** 上的数字减去 **1** 后的结果，再把 **黑板B** 上的数字修改成计算的结果"|STEP5: B = B - 1;||
|"6. 回到第3步执行"|STEP6: goto STEP3;||
|"7. 打印出 **黑板A** 上的数字"|STEP7: printf("%d", A);||
|"8. 结束执行"|STEP8: return 0;||


其实我们完全可以把这一串**翻译后的命令文本**称为程序：  
```C
  STEP1: A = 0;
  STEP2: B = 2;
  STEP3:<br>if(B == 0){<br>goto STEP7;<br>}<br>else{<br>goto STEP4;<br>}
  STEP4: A = A + 3;
  STEP5: B = B - 1;
  STEP6: goto STEP3;
  STEP7: printf("%d", A);
  STEP8: return 0;
```

而事实上，这就是一段C语言的代码，你可以在这个在线编程环境里不停点击“Next>”按钮尝试运行它。  
代码左侧的绿红箭头表示计算机刚执行完的代码命令和下一步要执行的代码命令，并且关注这个程序运行过程中，在右侧**Stack**下方的“黑板A”、“黑板B”以及右侧上方的“打印结果（Print output）”的数值变化：  
<iframe width="800" height="500" frameborder="0" src="https://pythontutor.com/iframe-embed.html#code=int%20main%28%29%20%7B%0A%20%20%0A%20%20int%20A%3B//%E8%BF%99%E8%A1%8C%E4%BB%A3%E7%A0%81%E7%9B%B8%E5%BD%93%E4%BA%8E%E4%B8%80%E4%B8%AA%E5%87%86%E5%A4%87%E6%AD%A5%E9%AA%A4%EF%BC%8C%E7%BB%99%E4%BA%86%E8%AE%A1%E7%AE%97%E6%9C%BA%E4%B8%80%E5%9D%97%E9%BB%91%E6%9D%BFA%0A%20%20int%20B%3B//%E8%BF%99%E8%A1%8C%E4%BB%A3%E7%A0%81%E7%9B%B8%E5%BD%93%E4%BA%8E%E4%B8%80%E4%B8%AA%E5%87%86%E5%A4%87%E6%AD%A5%E9%AA%A4%EF%BC%8C%E7%BB%99%E4%BA%86%E8%AE%A1%E7%AE%97%E6%9C%BA%E4%B8%80%E5%9D%97%E9%BB%91%E6%9D%BFA%0A%20%20%0A%20%20STEP1%3A%20A%20%3D%200%3B%0A%20%20STEP2%3A%20B%20%3D%202%3B%0A%20%20STEP3%3A%0A%20%20if%28B%20%3D%3D%200%29%7B%0A%20%20goto%20STEP7%3B%0A%20%20%7D%0A%20%20else%7B%0A%20%20goto%20STEP4%3B%0A%20%20%7D%0A%20%20STEP4%3A%20A%20%3D%20A%20%2B%203%3B%0A%20%20STEP5%3A%20B%20%3D%20B%20-%201%3B%0A%20%20STEP6%3A%20goto%20STEP3%3B%0A%20%20STEP7%3A%20printf%28%22%25d%22,%20A%29%3B%0A%20%20STEP8%3A%20return%200%3B%0A%20%20%0A%7D&codeDivHeight=400&codeDivWidth=350&cumulative=false&curInstr=0&heapPrimitives=nevernest&origin=opt-frontend.js&py=c_gcc9.3.0&rawInputLstJSON=%5B%5D&textReferences=false"> </iframe>



现在我们在回过头来观察一下这段程序的特点，从它的本质来定义 **程序**。

[点此可以查看以下代码的实际效果]:{{ "/reference/Example-Mouse2D.html" | relative_url }}