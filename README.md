## 参考
https://github.com/younghz/Markdown

-------------------------------
# 1.字体
## 1.1粗体
**Do not go gentle into that good night[^二十四个年头]**

[^二十四个年头]:不要温顺地走进那安息的长夜
## 1.2斜体
*Do not go gentle into that good night*

## 1.3删除线
~~Do not go gentle into that good night~~

## 1.4代码块
### 1.4.1其中一种
    print('Do not go gentle into that good night')



### 1.4.2行内高亮代码
可以直接从使用命令``import numapy as np``导入相应的库



### 1.4.3指定语言
**例如python语言**
```python
print('Do not go gentle into that good night')
```

### 1.4.4Markdown支持的常见代码块种类及关键字

+ **Shell**：bash , shell
+ **C**:cpp , c
+ **Java**:	java
+ **JavaScript**:js , jscript , javascript
+ **PHP**:php
+ **Python**:	py , python
+ **SQL**:sql
+ **matlab**:matlab
+ **GO**:go , golang
+ **R**:r , s , splus
+ **tex**:tex



## 1.5脚注

这里有一只只因[^只因]。


[^只因]:鸡（小黑子）

# 2.引用
*Do not go gentle into that good night*
>狄兰·托马斯[^迪兰·托马斯]
>>狄兰·托马斯
>>>狄兰·托马斯

[^迪兰·托马斯]:迪伦·托马斯（Dylan Thomas，1914.10.27 －1953.11.9)，威尔士诗人。出生于威尔士的斯旺西。父亲是学校的英文教师，迪伦从中学时代就显露出诗歌天分，毕业后当了报社记者。出版了一系列诗集，也从事剧本和小说创作。1950-1953年间三度前往美国。于1953年在纽约病逝。

## 1.6自定义风格

<font color="red" size="60pt">注意:</font>
<p style="color : red ;font : normal 26pt '微软雅黑'">hello</p>



# 2.图片插入

## 2.1简单插入图片
![阿库娅](aky.jpg) ![asuka](asuka.png)
## 2.2图片居中并排显示(可以调节大小)
<center class="half">
<img src="fig/aky.jpg" width=200/>
<img src="fig/asuka.png" width=237/>
</center>

## 2.3图片左对齐并排显示

<figure>
<img src="fig/sleep.jpg" width=140/>
<img src="fig/sleep.jpg" width=140/>
<img src="fig/sleep.jpg" width=140/>
</figure>


## 2.4并排显示在表格中且加上下表图注

\<tr>：表示 table row ——同一行的内容都放到这个标签中  

\<td>：表示 table data,——每一张图片的数据都放在这个里


单纯的整活(~~没有别的意思~~)
<table>
    <tr>
        <td ><center><img src="https://ts1.cn.mm.bing.net/th/id/R-C.51dc415e53dd6a7b7d8cb51b6f7d872a?rik=lXRUjErSLUPHPg&riu=http%3a%2f%2faramajapan.com%2fwp-content%2fuploads%2f2018%2f11%2faramajapan.com-yui-aragaki2.jpg&ehk=I6bmRAEXPMStMBLqFERnwN0phu7Ik88QqKfpFt3Y5EM%3d&risl=&pid=ImgRaw&r=0" >Fig1  新垣结衣 </center></td>
        <td ><center><img src="https://ts1.cn.mm.bing.net/th/id/R-C.51dc415e53dd6a7b7d8cb51b6f7d872a?rik=lXRUjErSLUPHPg&riu=http%3a%2f%2faramajapan.com%2fwp-content%2fuploads%2f2018%2f11%2faramajapan.com-yui-aragaki2.jpg&ehk=I6bmRAEXPMStMBLqFERnwN0phu7Ik88QqKfpFt3Y5EM%3d&risl=&pid=ImgRaw&r=0"  >Fig2 新垣结衣</center></td>
    </tr>
    <tr>
        <td><center><img src="fig/g5.png" >Fig3 John</center></td>
        <td ><center><img src="fig/g5.png"  >Fig4 John</center> </td>
    </tr>
</table>

## 2.5表情(Markdown自带的emoji)

[各种表情指令汇总链接](https://www.webfx.com/tools/emoji-cheat-sheet/)

:smile:
:sweat_smile:(:older_man:最爱的流汗黄豆)



# 3.超链接

## 3.1行内式

[cvpr_seminar_006](https://github.com/lzu-cvpr/cvpr_seminar_006)

## 3.2参考式

[cvpr_seminar_006][1]

[1]:https://github.com/lzu-cvpr/cvpr_seminar_006


## 3.3直接链接
~~<https://www.pronhub.com>~~(搞错了)
![战锤jpg](fig/zc.jpg)
<https://www.marxists.org/chinese/index.html>(这才是当代青年应该学习的)


## 3.4文章内的链接
跳转到文章内某处:[引用](#引用)


# 4.表格

用`|`表示表格纵向边界，表头和表内容用`-`隔开，并可用`:`进行对齐设置，两边都有`:`则表示居中，若不加`:`则默认左对齐

|网站                              |链接                                |
|:------------------------------------:|------------------------------------|
|114                              |[https://github.com/marmotxcw/markdown-beamer](https://github.com/marmotxcw/markdown-beamer)|
|514                              |[https://github.com/marmotxcw/markdown-beamer](https://github.com/marmotxcw/markdown-beamer)|




# 5.列表
**无标号的**
+ 啊
- 哼哼啊哼啊
+ 啊啊啊啊啊啊啊

---------------------------
**有标号的**

1. 正确的
2. 中肯的
3. 客观的

---------------------------

**嵌套**

1.练习生
  + 唱
  + 跳
  + rap
  + 篮球



# 6.公式
**类似于latex**


$\alpha$,$\beta$,$\omega$

$$e^{ix}=\cos x+i\sin x $$

$$e^{ix}=\cos x+i\sin x \tag{6.1}$$



$$
\begin{aligned}
    x&=108943+4782+789\\
    &=113725+789\\
    &=114514
\end{aligned}
$$


# 7.分割线(三种)

----------------------------------


**********************************


______________________________________


# 8.VScode中需要的插件(用typora也可)
1. Markdown all in one
2. Markdown Preview Enhanceed(边写便查看)

# 9.Markdown如何保存为pdf

## 9.1方法一
用浏览器打开然后，对页面打印保存成pdf。



## 9.2方法二
对vscode中预览的页面右键点击chrome，选择其中的pdf格式。

************************
![example1](fig/example1.png)
************************


<!-- # 10.专注模式

+ 进入：Ctrl+k z
+ 退出：按两次Esc -->






