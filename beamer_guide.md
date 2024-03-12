
*目前最流行的 LaTeX 幻灯片工具为 beamer 文档类，它以页面（被称为「帧」）为基本组织单位，提供丰富的功能选项和许多预定义的风格主题，支持各种编译程序。*(**beamer作者在用户手册叨叨不少内容，基本的意思就是，我这个关于幻灯片的设计理念已经足够了，你就不要想花样了，比方你想把标题栏放在页脚行不行，当然行，但是不要这样干，没啥意义。言下之意就是在使用beamer进行幻灯片或者叫slides的设计时，我们已经认同了slides应该遵从这种类型的布局风格。**)


# 1.主题

## 1.1使用默认主题

修改 beamer 幻灯片格式的基本方式是使用主题。beamer 提供了 20 多种不同的幻灯片风格，可以在导言区使用 `\usetheme `命令自主选择：

**例如**：`\usetheme{PaloAlto}`

其中**官方**的主题可以参考这个[网页](https://mpetroff.net/files/beamer-theme-matrix/)


其他许多的**非官方**的主题的模板可以参考这个[仓库](https://links.jianshu.com/go?to=https%3A%2F%2Fgithub.com%2Fmartinbjeldbak%2Fultimate-beamer-theme-list)



+ `\useinnertheme`：选择内部主题,内部主题主要控制的是标题页、列表项目、定理环境、图表环境、脚注等一帧以内的内容格式。预定义的内部主题有：
   + default
   + circles
   + rectangles
   + rounded
   + inmargin



+ `\useoutertheme`：选择外部主题,外部主题主要控制的是幻灯片顶部尾部的信息栏、边栏、图表、帧标题等一帧以外的内功格式。预定义的外部主题有：

  + default
  + infolines
  + miniframes
  + smoothbars
  + sidebar
  + split
  + shadow
  + tree
  + smoothtree
+ `\usecolortheme`：选择色彩主题,色彩主题控制各个部分的色彩。预定义的色彩主题有：

    + default
    + albatross
    + beaver
    + beetle
    + crane
    + dolphin
    + dove
    + fly
    + lily
    + orchid
    + rose
    + seagull
    + seahorse
    + sidebartab
    + structure
    + whale
    + wolverine


+ `\usecolortheme`：选择字体主题,字体主题则控制幻灯片的整体字体风格。预定义的字体主题有：
  + default：无衬线字体
  + professionalfonts：不对字体有特别的设置
  + serif：衬线字体
  + structurebold
  + structureitalicserif
  + structuresmallcapsserif



**以上各种设置具体可选项及其效果可自行搜索或者查阅官方的用户手册。**

## 1.2自定义风格

beamer 使用一种模板机制，将幻灯片的不同内容组件格式抽象为模板代码、模板字体、模板色彩，模板代码是实现组件的具体代码。在 beamer 中，提供了许多自定义的设置命令让用户自定义幻灯片风格：


+ `setbeamercolor`：设置组件的色彩
+ `setbeamerfont`：设置组件字体
+ `setbeamertemplate`：设置组件模板的具体实现代码(自定义组件)



例如自己设置前景和背景颜色`\setbeamercolor{mycolor}{fg=blue,bg=red}`,其中第一个括号相当于自己定义的一种颜色风格。

另外还可以指定颜色深度或者进行颜色的混合如
`\setbeamercolor{mycolor}{fg=blue!20!,bg=red!30!}`
和`\setbeamercolor{mycolor}{fg=blue,bg=red!20!green!30!}`。

同时该指令的前一个花括号可以为指定的部分修改颜色如`\setbeamercolor{normal text}{fg=red}`。

例如对于 itemize 列表，可以设置


```tex
\setbeamertemplate{itemize items}[circle]
\setbeamercolor{itemize item}{fg=black}
\setbeamercolor{itemize/enumerate body}{fg=gray}
\setbeamerfont{itemize/enumerate body}{family=\rmfamily}
```

例如对于字体的简单自定义设置

```tex

\setbeamerfont{normal text}{family=\chalkd,series=\mdseries}
\setbeamerfont{alerted text}{family=\chalkd,series=\bfseries}
\setbeamerfont{frametitle}{family=\chalkd,series=\bfseries}
size={\fontsize{32}{36}}

```
全文字体大小设置为`\documentclass[UTF8,handout,10pt]{ctexbeamer}`





对于简单的样式修改通过组合现有的主题和背景插图来完成，但对 beamer 进行更详细的样式定制时，字体、色彩、模板名目繁多，可能需要参考在安装目录下 `theme/ `目录中的模板源代码。beamer 的每一个主题对应一个后缀为 `.sty `的主题文件，可以查看官方手册，定制自己的主题文件.





## 2.三种列举的形式：


### 2.1itemize:分条目

```tex
\begin{itemize}
\item[*] a
\item[*] b
\end{itemize}
```

item的方括号里的内容是为定制前面的符号，可以不要（连同括号），那么前面的符号就是默认的黑点，也可以换为其他的符号如`* - +`等。


itemize也可以嵌套使用
```tex
 \begin{itemize}
   \item  First Level
   \begin{itemize}
     \item  Second Level
     \begin{itemize}
       \item  Third Level
       \begin{itemize}
         \item  Fourth Level
       \end{itemize}
     \end{itemize}
   \end{itemize}
 \end{itemize}

```


**默认的编号格式：**
+ Level 1 是 \textbullet (•),
+ Level 2 是 \textendash (–) ,
+ Level 3 是 \textasteriskcentered (*)
+ Level 4 是 \textperiodcentered (·).

### 2.2enumerate:编号
```tex
\begin{enumerate}[1)]
\item a
\item b
\end{enumerate}

```
方括号里的内容是定制前面的编号的形式，可以不加，默认就是简单的数字，也可以换成[step 1],[(i)]等，LaTeX可以自动识别。但是要注意，使用了方括号，必须在前面加`\usepackage{enumerate}`。

### 2.3description:描述

```tex
\begin{description}
\item[fuc] a
\item[fuc] b
\end{description}

```
方括号的词会作为一个描述出现在item的前面。











# 3.内容

## 3.1首页


幻灯片首页也是 beamer 中的一帧，其显示内容也是要在帧环境中设置。但首页又往往和其它页不一样，需要显示整个幻灯的标题、小标题、作者、学院、日期、标题图形等。beamer 在导言区为首页提供了显示相对应内容的命令，在首页帧中需要通过使用 `\maketitle`或者 `\titlepage` 使得这些内容显示到首页帧中。


```tex
\title{杂谈勾股定理}
\subtitle{数学史讲座之一}
\author{BlueHeart}        
\institute{九章学堂}
\date{\today}
\begin{document}
    \begin{frame}
        \maketitle % 等价于 \titlepage
    \end{frame}
    % ...
\end{document}

```



## 3.2帧frame

在 beamer 中，帧用 frame 环境得到。一帧里面的内容可以使用各种常见的 LaTeX 命令和环境。在每一帧当中，内容有一定的水平边距，并且整体垂直居中显示。幻灯片每一帧通常都有标题，甚至还有小标题：

```tex
\begin{frame}
    \frametitle{标题}
    \framesubtitle{小标题}
    打个胶先
\end{frame}
% 标题和小标题还可以有下面更简洁的方式
\begin{frame}{标题}{小标题}
    先打个胶
\end{frame}

```




空白帧

额外帧，导入包`\usepacage{appendixnumberbeamer}`,将内容置于附录即`\appendix`之后。




## 3.3分节

和一般文档类一样，在 beamer 中可以使用 section、subsection、subsubsection 以及 `\part` 命令对幻灯片分节，然后使用 `\tableofcontents` 命令产生目录。目录页也是帧，需要在目录帧中通过使用 `\tableofcontents` 才能产生目录并将其显示到目录帧中。



`\part` 命令本身不产生标题，但 beamer 提供了一个 `\partpage` 命令，它和 `\titlepage` 命令类似，可以在一帧中产生文档某部分的标题。一个完整的演讲报告 beamer 文档一般控制在几十帧的篇幅，使用 `\part` 和 `\section` 至 `\subsubsection` 的命令进行分节足以。但如果希望将所有很多次的演讲报告内容放进同一个单独的文件，则可以使用 `\lecture` 命令进行更高一层的内容划分。


## 3.4目录

beamer 中的 `\tableofcontents `可以在可选参数中使用许多参数控制其格式：

+ \tableofcontents[currentsection]：只显示当前一节的目录结构
+ \tableofcontents[currentsubsection]：只显示当前一小节的目录结构

## 3.5定理和区块

类似定理环境的彩色框效果，beamer 还提供了其他的区块环境，可以用于强调一部分内容。beamer 提供了三种区块环境：

+ block
+ alertblock
+ exampleblock

例如：
```tex
\begin{block}{定义、定理、证明等}



\end{block}
```

类似的还有定理类环境：


定义
```tex
\begin{definition}[小黑子]



\end{definition}
```

定理
```tex
\begin{theorem}[篮球]



\end{theorem}
```

证明
```tex
\begin{proof}[练习生]



\end{proof}
```

推论


```tex
\begin{corollary}{鸡}


\end{corollary}
```



事实

```tex
\begin{fact}{rap}



\begin{fact}

```





例子


```tex
\begin{example}{只因}



\end{example}
```



## 3.6图标的使用

在 beamer 中使用图表和在一般文档中的语法并无区别。不过由于 beamer 是按帧组织内容的，位置固定，因此 figure 和 table 环境不再是浮动的环境。


其中在帧内的图片插入的方法和latex插入图片区别不大

```tex
\begin{frame}{标题}{小标题}
 \begin{figure}[H]
	\centering
	\includegraphics[width=0.70\textwidth]{3.png}
	\caption{图例名称}
\end{figure}
\end{frame}

```


幻灯片中的表格务求简明清晰，可以考虑使用行色彩相间的彩色表格。xcolor 宏包通过加上 table 选项就可以实现给表格行加上颜色。由于 beamer 本身就会载入 xcolor 宏包，因此可以直接在 beamer 参数中设置：



设置**幻灯片的LOGO**，通常是单位或者学校机构的LOGO，一般放在右下角，\logo 命令一般放在导言区：如`\pgfdeclareimage[height=0.5cm]{lzu-logo}{lzu-logo.pdf}`,或者使用命令`\logo{}`、
`\logo{\includegraphics{logo.pdf}}`




```tex
\documentclass[xcolor=table]{beamer}
\begin{frame}
    \rowcolors{2}{blue!25}{blue!50}
    \begin{tabular}{ccc}
        \rowcolor{green}x & y & z \\
        3 & 4 & 5 \\
        5 & 12 & 13 \\
    \end{tabular}
\end{frame}

```
其中，`\rowcolors{n}{color}...{color} `命令使用来表格除去首行外，连续  行的背景颜色设定，并以$n$为周期循环。而 `\rowcolor{color} `命令用来在表格中单独设置一行的背景颜色。




## 3.7参考文献的使用

在 beamer 中添加参考文献列表与一般文档的语法没有区别，不过与书面的文稿不同，在幻灯片中通常并不适合特别冗长的文献列表，列出的条目不宜过多，也不需要文献编号。因此，beamer 中的文献列表，文字排版比较宽松，列表前没有标题，默认格式也是没有编号的（因为幻灯片很难前后跳跃翻页，因此编号引用用途不大）。


# 4.幻灯片动态

## 4.1覆盖

覆盖是最为基本的一种幻灯片效果，它是把同一帧幻灯片的不同内容按一定次序拆分成几页显示出来。利用覆盖可以让内容逐步显示，也可以让不同内容依次替代，产生类似动画的效果。



逐条显示是最为常用的覆盖效果，其基本命令是 `\pause`，表示幻灯片在此处会停顿一下，在` \pause` 后面的所有内容会在 pdf 文件的下一页显示。

例如在同一帧幻灯片内按顺序播放

```tex

\begin{frame}
    \frametitle{小黑子}
    \framesubtitle{小标题}
    \pause \item 个人练习生
    \pause \item 练习两年半
    \pause \item 唱跳rap篮球
\end{frame}

```


对于目录帧，可以给目录命令加上选项使得目录在一项后面暂停。


```tex
\begin{frame}{目录}
    \tableofcontents[pausesections]
\end

```


更为一般的是 `\onslide`，它可以指定内容在一帧中的第几步显示，使用 `\onslide` 时「不显示的内容还占用原来的位置」。在 `\onslide` 后面的尖括号中的内容就是覆盖步骤的设置。覆盖语法支持单个的步骤，也支持多个步骤和区间。





命令`\onslide{}`奖括号里的内容作为逻辑上的下一张幻灯片进行播放，例如

```tex
\begin{frame}
    \frametitle{小黑子}
    \framesubtitle{小标题}
    \onslide<2->{ \item 个人练习生
    \onslide<3->{ \item 练习两年半
    \onslide<4->{ \item 唱跳rap篮球

    }
    }
    }
\end{frame}
```


`\only` 命令与 `\onslide` 命令类似，不过 `\only` 命令「在不显示的步骤没有额外的占位」，可以得到内容代替的效果。

```tex
\begin{frame}
    计数：\only<1>{1}\only<2>{2}\only<3>{3}\only<4->{4}

    \onslide<5>数完了
\end{frame}

```

**这种使用尖括号表示步骤的覆盖语法，实际上在 beamer 的很多命令和环境后面都可以使用，比如：**

```tex
% 加粗
\begin{frame}
    \textbf<3>{只在第三步加粗}
\end{frame}
% 定理
\begin{frame}
    \begin{theorem}<2->
        第二步以后显示定理
    \end{theorem}
\end{frame}
% 列表
\begin{frame}
    \begin{itemize}
        \item<1-> 开始显示
        \item<3-> 最后显示
        \item<2-> 然后显示
    \end{itemize}
\end{frame}

```



在覆盖语法中，使用 + 号就类似使用了 `\pause`，这可以避免手工计数。连续使用多个 `\item<+->` 就可以表示` \item<1->`、`\item<2->`、`\item<3->` …… 的效果。此外，还可以在整个 enumerate 和 itemize 环境后面加上 `[<+->]` 的可选项，相当于对每个 `\item` 后面都使用了 `<+->`，非常方便：


## 4.2动画效果和动态演示


beamer 还支持 pdf 页面的动画切换效果，这些效果只在 pdf 文件全屏观看是时有效。比如，可以设置一帧中的第二步为页面从左边飞入：


```tex
\begin{frame}{动画切换}
    \only<1>{旧内容}
    \only<2>{新内容}
    \transcover<2>
\end{frame}
```


beamer 支持的** pdf 页面切换效果**如下表：


命令                              |效果                                |
|:------------------------------------:|------------------------------------|
|`\transblindshorizontal`                              |水平百叶窗|
|`\transblindsvertical `                             |	垂直百叶窗|
|`\transboxin`|	盒状收缩|
|`\transboxout`|	盒装展开|
|`\transcover`|	新页面飞入，覆盖旧页面|
|`\transdissolve`|	溶解|
|`\transfade`|	渐显|
|`\transglitter`|闪烁（与溶解类似）|
|`\transpush`|新页面推进，推走旧页面|
|`\transsplitverticalin`|	垂直收缩|
|`\transsplitverticalout`|垂直展开|
|`\transsplithorizontalin`|	水平收缩|
|`\transsplithorizontalout`|水平展开|
|`\transuncover`|	旧页面飞走，揭开新页面|
|`\transwipe`|沿直线消除旧页面|


beamer 的一个附属包 multimedia 可以用来在 pdf 幻灯片中嵌入视频、音频等多媒体信息。multimedia 提供视频的基本命令是 `\movie`：


```tex
\movie[可选项]{文字}{多媒体文件名}
```



类似地，`\sound` 命令用来在 pdf 幻灯片中插入音频：



```tex
\usepackage{multimedia}
% 导言区
% ……
\begin{frame}
    % 自动播放，无显示内容
    \sound[autostart]{}{foo.au}
\end{frame}
```

**插入网址的命令**:`\href{}`


消除幻灯片中的导航线`\setbeamertemplate{navifation symbols}{}`



handout选项：**取消你幻灯片中放映,即取消重复的幻灯片**

```tex
\documentclass[handout]{beamer}
```










# 5.可以用于参考的资料

## 5.1Latex相关

+ Overleaf: 在线协作式 LaTeX 编辑器(其中有不少Latex模板)
    + 在线网址:https://cn.overleaf.com/
    + Github项目:https://github.com/overleaf/overleaf

+ [一个Latex的简易手册](https://github.com/sailist/LaTeXdoc/releases/download/0.7/LaTeX.pdf),[相应Github项目](https://github.com/sailist/LaTeXdoc)
+ LaTeX入门——刘海洋

## 5.2beamer相关

+ [Beamer 快速入门](https://links.jianshu.com/go?to=https%3A%2F%2Fwww.latexstudio.net%2Farchives%2F51706.html)
+ [Beamer 3.0 指南 中译本](https://links.jianshu.com/go?to=https%3A%2F%2Fwww.latexstudio.net%2Farchives%2F51704.html)
+ [Beamer用户手册(V3.24)中译版](https://links.jianshu.com/go?to=https%3A%2F%2Fwww.latexstudio.net%2Farchives%2F9457.html)
+ [Beamer用户手册英文版](https://links.jianshu.com/go?to=https%3A%2F%2Fmirror.bjtu.edu.cn%2Fctan%2Fmacros%2Flatex%2Fcontrib%2Fbeamer%2Fdoc%2Fbeameruserguide.pdf)
+ [使用 Beamer 制作学术讲稿](https://links.jianshu.com/go?to=https%3A%2F%2Fwww.latexstudio.net%2Farchives%2F2825.html)
+ [Beamer v3.0 Guide](https://links.jianshu.com/go?to=http%3A%2F%2Fstatic.latexstudio.net%2Fwp-content%2Fuploads%2F2014%2F12%2Fbeamer_guide.pdf)




# 6.额外内容
暂时不知道总结到哪一部分先放在这里再说




+ 使用侧边栏：`\useoutertheme[]{sidebar}`


+ 调整整体长宽比：`\\documentclass[aspectratio=169]{beamer}`,例如此时长宽比为16：9。


+ 让你的公式更加优雅：使用指令`\usefonttheme[onlymath]{serif}`使得幻灯片里面的公式正常斜体。


+ 2个功能相仿的换页命令：`\newpage`，`\clearpage`
区别：单栏时没有区别，双栏时\newpage是换到新的列！而\clearpage才是真正的换到新的页！































