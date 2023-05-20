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
想象一下在非计算机领域的语境下我们提到“程序”时一般会怎么说？我们会说“要完成这个事情需要经过这么一个**程序**（或者**过程/步骤**），第一步...第二步...”。  
在计算机领域也是如此，把计算机想象成一个只能执行一些*固定功能*（比如：加减乘除、判断是或否）的机器人，此时你要指挥它完成一项工作，你必须考虑到它能做的这些*固定功能*，然后明确地告诉它用怎么样的**步骤**来执行它会的这些基本操作，从而完成这个复杂工作。  

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

<div class="language-plaintext highlighter-rouge"><div class="highlight"><pre class="highlight"><code>1. 在 <b>黑板A</b> 上写下 <b>0</b>
2. 在 <b>黑板B</b> 上写下 <b>2</b>
3. 判断 <b>黑板B</b> 上的数字，如果等于 <b>0</b> 就执行<b>第7步</b>命令；否则执行<b>第4步</b>命令
4. 计算 <b>黑板A</b> 上的数字加上 <b>3</b> 后的结果，再把 <b>黑板A</b> 上的数字修改成计算的结果
5. 计算 <b>黑板B</b> 上的数字减去 <b>1</b> 后的结果，再把 <b>黑板B</b> 上的数字修改成计算的结果
6. 回到<b>第3步</b>执行
7. 打印出 <b>黑板A</b> 上的数字
8. 结束执行
</code></pre></div></div>

现在你可以把自己当作计算机，用我准备的这两块“黑板”执行上面这一串命令：  
<label for="fname">黑板A上的数字:</label>
<input type="text" id="fname" name="fname">
<label for="lname">黑板B上的数字:</label>
<input type="text" id="lname" name="lname"><br>
<label for="nextInstruction">下一步你要执行第几条命令:</label>
<input type="text" id="nextInstruction" name="nextInstruction">
<label for="print">你打印出来的结果:</label>
<input type="text" id="print" name="print"><br>

如果我们仔细观察上面的这段程序，虽然它是一段自然语言，但是它的结构非常固定，比如：

- “在 **某黑板** 上写下 **某个数**”
- “计算 **某黑板** 上的数字 **加/减** 去 **某数字** 的结果”

那么我们是否可以总结这个固定结构的规律，定义一个规则将上述程序“翻译”成更简单的固定结构文本呢？当然可以：  

|程序的命令原文|翻译后的命令文本|翻译规则讲解|
|:----|:----|:----|
|"1. 在 **黑板A** 上写下 **0**"|STEP1: A = 0;|用“STEP1:”表示是第1步指令，用字母“A”表示黑板A，用“=”表示要向“=”左边的黑板上写下一个数，指令最后用分号表示这条指令结束|
|"2. 在 **黑板B** 上写下 **2**"|STEP2: B = 2;|同上类似|
|"3. 判断 **黑板B** 上的数字，如果等于 **0** 就执行**第7步**命令；否则执行**第4步**命令"|STEP3:<br>if(B == 0){<br>goto STEP7;<br>}<br>else{<br>goto STEP4;<br>}|用“if(B==0)”表示“判断黑板B上的数字是否等于0”，<br>用紧跟着的{}里的指令表示如果黑板B上的数字等于0（即"B==0"时）则计算机要执行的命令，也就是“goto STEP7;”——让计算机跳转去执行第7步命令，<br>用"else{goto STEP4;}"大括号里的内容表示前面"if()"里的条件不满足时（也就是黑板B上不是0时），<br>计算机该执行的命令则是跳转去执行第4步命令。|
|"4. 计算 **黑板A** 上的数字加上 **3** 后的结果，再把 **黑板A** 上的数字修改成计算的结果"|STEP4: A = A + 3;|用“STEP4:”表示是第4步指令，用字母“A”表示黑板A，用“=”表示要向“=”左边的黑板上写下一个数，“A + 3”表示计算黑板A上面的数字加上3的结果，分号表示这条指令结束。<br>计算机会从右到左理解整行指令：用黑板A上现有的数字加3，并把计算结果写在黑板A上。|
|"5. 计算 **黑板B** 上的数字减去 **1** 后的结果，再把 **黑板B** 上的数字修改成计算的结果"|STEP5: B = B - 1;|同上条类似，只是“B - 5”表示计算黑板B上现有的数字减去1的结果|
|"6. 回到第3步执行"|STEP6: goto STEP3;|“STEP6:”表示是第6步指令，“goto STEP3”表示让计算机跳转去执行第3条指令，分号表示这条指令结束|
|"7. 打印出 **黑板A** 上的数字"|STEP7: printf("%d", A);|“printf”表示让计算机打印其后的括号里的值，<br>“("d",A)”则表示打印的具体内容是黑板A上的整数<br>（"d"相当于是提醒计算机，把A上的数字当整数打印出来）|
|"8. 结束执行"|STEP8: return 0;|“return 0;”表示告诉计算机整个程序运行到此结束|

其实我们完全可以把表格第二列这一串**翻译后的命令文本**称为程序：  
{% highlight c %}
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
{% endhighlight %}  

事实上，这就是一段C语言的程序代码，你可以在下方这个在线编程环境里不停点击“Next>”按钮尝试运行它。  
> 在线环境使用简介：代码左侧的绿红箭头表示计算机刚执行完的代码命令和下一步要执行的代码命令；你可以关注这个程序运行过程中，在右侧**Stack**下方的“黑板A”、“黑板B”以及右侧上方的“打印结果（Print output）”的数值变化。  
<iframe width="800" height="500" frameborder="0" src="https://pythontutor.com/iframe-embed.html#code=//%E6%B3%A8%E6%84%8F%EF%BC%9A%E4%B8%8B%E9%9D%A2%E4%BB%A3%E7%A0%81%E9%87%8C%E6%AF%8F%E8%A1%8C%E7%9A%84%22//%22%E5%8F%B3%E8%BE%B9%E7%9A%84%E5%86%85%E5%AE%B9%E9%83%BD%E6%98%AF%E6%B3%A8%E9%87%8A%EF%BC%8C%0A//%E4%BB%A3%E7%A0%81%E5%9C%A8%E8%A2%AB%E7%BC%96%E8%AF%91%E5%99%A8%E8%BD%AC%E6%8D%A2%E6%88%90%E8%AE%A1%E7%AE%97%E6%9C%BA%E5%8F%AF%E4%BB%A5%E7%90%86%E8%A7%A3%E5%92%8C%E5%92%8C%E6%89%A7%E8%A1%8C%E7%9A%84%E4%BA%8C%E8%BF%9B%E5%88%B6%E6%96%87%E4%BB%B6%E4%B9%8B%E5%89%8D%EF%BC%8C%0A//%E7%BC%96%E8%AF%91%E5%99%A8%E4%BC%9A%E5%85%88%E7%9B%B4%E6%8E%A5%E6%8A%8A%E6%B3%A8%E9%87%8A%E9%83%BD%E5%88%A0%E9%99%A4%EF%BC%8C%0A//%E6%B3%A8%E9%87%8A%E5%AD%98%E5%9C%A8%E7%9A%84%E7%9B%AE%E7%9A%84%E5%8D%95%E7%BA%AF%E7%9A%84%E6%98%AF%E7%BB%99%E6%88%91%E4%BB%AC%E8%87%AA%E5%B7%B1%E6%88%96%E8%80%85%E5%85%B6%E4%BB%96%E8%AF%BB%E6%88%91%E4%BB%AC%E4%BB%A3%E7%A0%81%E7%9A%84%E4%BA%BA%E6%8F%90%E7%A4%BA%E7%94%A8%E7%9A%84%EF%BC%8C%0A//%E6%89%80%E4%BB%A5%E4%BD%A0%E5%8F%AF%E4%BB%A5%E7%9B%B4%E6%8E%A5%E5%BD%93%E6%89%80%E6%9C%89%E7%9A%84%E6%B3%A8%E9%87%8A%E4%B8%8D%E5%AD%98%E5%9C%A8%0A%0Aint%20main%28%29%20%7B%0A%20%20%0A%20%20int%20A%3B//%E8%BF%99%E8%A1%8C%E4%BB%A3%E7%A0%81%E7%9B%B8%E5%BD%93%E4%BA%8E%E4%B8%80%E4%B8%AA%E5%87%86%E5%A4%87%E6%AD%A5%E9%AA%A4%EF%BC%8C%E7%BB%99%E4%BA%86%E8%AE%A1%E7%AE%97%E6%9C%BA%E4%B8%80%E5%9D%97%E9%BB%91%E6%9D%BFA%0A%20%20int%20B%3B//%E8%BF%99%E8%A1%8C%E4%BB%A3%E7%A0%81%E7%9B%B8%E5%BD%93%E4%BA%8E%E4%B8%80%E4%B8%AA%E5%87%86%E5%A4%87%E6%AD%A5%E9%AA%A4%EF%BC%8C%E7%BB%99%E4%BA%86%E8%AE%A1%E7%AE%97%E6%9C%BA%E4%B8%80%E5%9D%97%E9%BB%91%E6%9D%BFB%0A%20%20%0A%20%20//%E4%BB%A5%E4%B8%8B%E5%B0%B1%E6%98%AF%E6%88%91%E4%BB%AC%E7%BF%BB%E8%AF%91%E5%87%BA%E6%9D%A5%E7%9A%84%E6%8C%87%E4%BB%A4%EF%BC%8C%E5%AE%83%E5%85%B6%E5%AE%9E%E5%B0%B1%E6%98%AF%E4%B8%80%E6%AE%B5C%E8%AF%AD%E8%A8%80%E4%BB%A3%E7%A0%81%EF%BC%8C%0A%20%20//%E8%A6%81%E8%BF%90%E8%A1%8CC%E8%AF%AD%E8%A8%80%E4%BB%A3%E7%A0%81%E5%BF%85%E9%A1%BB%E5%B0%86%E4%BB%A3%E7%A0%81%E6%94%BE%E5%9C%A8int%20main%28%29%20%7B%7D%E7%9A%84%E5%A4%A7%E6%8B%AC%E5%8F%B7%E4%B9%8B%E4%B8%AD%EF%BC%8C%0A%20%20//C%E8%AF%AD%E8%A8%80%E7%9A%84%E7%BC%96%E8%AF%91%E5%99%A8%E6%89%8D%E8%83%BD%E8%AF%86%E5%88%AB%E5%AE%83%E5%B9%B6%E6%8A%8A%E5%AE%83%E7%BC%96%E8%AF%91%E6%88%90%E4%BA%8C%E8%BF%9B%E5%88%B6%E6%96%87%E4%BB%B6%EF%BC%8C%E6%9D%A5%E8%AE%A9%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%90%86%E8%A7%A3%E5%92%8C%E8%BF%90%E8%A1%8C%0A%20%20STEP1%3A%20A%20%3D%200%3B%0A%20%20STEP2%3A%20B%20%3D%202%3B%0A%20%20STEP3%3A%0A%20%20if%28B%20%3D%3D%200%29%7B%0A%20%20goto%20STEP7%3B%0A%20%20%7D%0A%20%20else%7B%0A%20%20goto%20STEP4%3B%0A%20%20%7D%0A%20%20STEP4%3A%20A%20%3D%20A%20%2B%203%3B%0A%20%20STEP5%3A%20B%20%3D%20B%20-%201%3B%0A%20%20STEP6%3A%20goto%20STEP3%3B%0A%20%20STEP7%3A%20printf%28%22%25d%22,%20A%29%3B%0A%20%20STEP8%3A%20return%200%3B%0A%20%20%0A%7D&codeDivHeight=400&codeDivWidth=350&cumulative=false&curInstr=0&heapPrimitives=nevernest&origin=opt-frontend.js&py=c_gcc9.3.0&rawInputLstJSON=%5B%5D&textReferences=false"> </iframe>  

<br>
现在我们在回过头来观察一下这段程序的特点，尝试从它的本质来定义 **程序**：  
程序就是我们指挥计算机，按照一定的**流程**、用它拥有的**固定功能**完成一个任务所编写的代码；它由一连串命令按照某种顺序构成，每个命令从组成上来看包含了告诉计算机需要做什么（what to do）、怎么做（how to do）的信息。“做什么”的信息我们可以称之为指令（instruction），“怎么做”的部分则包含在我们给它的数据（data）里。  
> 比如“A = A + 3”这条命令中的指令就是“+”和“=”、数据是“A”和“3”：计算机，请你执行加法，并把加法结果记录下来；加法（“+”）执行的的方式是使用黑板A上现有的数字和数字3相加、记录结果（“=”）的执行方式是把刚刚算完的加法结果再写到黑板A上。  

所以可以说，程序 = ( 指令 + 数据 ) X 流程，而编程，就是编写这样的程序的过程。

[点此可以查看以下代码的实际效果]:{{ "/reference/Example-Mouse2D.html" | relative_url }}
