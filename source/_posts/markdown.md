---
title: Markdown基础语法教程
date: 2020-12-08 23:43:55
tags: Markdown
categories: 写作
img: https://i.loli.net/2021/08/11/RUWrwCOejByZdNE.jpg
#password: af89b3b3afc476d87401059ae58ce2e0d1f93567e4a07ccc19233571c5b44977 #设置密码（yml中开启相应功能）

---
<img src="https://ss3.bdstatic.com/70cFv8Sh_Q1YnxGkpoWK1HF6hhy/it/u=1750208429,1514486128&fm=26&gp=0.jpg" width="100%">

## 简介

>&emsp;&emsp;Markdown是一种轻量级标记语言，创始人为约翰·格鲁伯（英语：John Gruber）。 它允许人们使用易读易写的纯文本格式编写文档，然后转换成有效的XHTML（或者HTML）文档。这种语言吸收了很多在电子邮件中已有的纯文本标记的特性...<br>
>&emsp;&emsp;由于Markdown的轻量化、易读易写特性，并且对于图片，图表、数学式都有支持，目前许多网站都广泛使用Markdown来撰写帮助文档或是用于论坛上发表消息。 如GitHub、Reddit、Diaspora、Stack Exchange、OpenStreetMap 、SourceForge、简书等，甚至还能被使用来撰写电子书...
## 标题
------------
### `=` 和 `-` 标记一级和二级标题
	一级标题
	=================
	
	二级标题
	-----------------
	
如图所示：
![单个字符可能出现不兼容情况！建议多个字符！](https://i.loli.net/2020/12/29/foV4IqbsHe6J53w.gif)

### `#`号标记标题

	# 一级标题
	## 二级标题
	### 三级标题
	#### 四级标题
	##### 五级标题
	###### 六级标题

如图所示：
![](https://i.loli.net/2020/12/29/4DhslHIz7gQNue8.gif)

## 文本
------------
### 空格
    &emsp;//全角空格（中文）
	&nbsp;//半角空格（英文）
	
如图所示：
![](https://i.loli.net/2020/12/29/Xc9KWuE3iOr5D21.gif)
### 斜体
	*斜体文本*
	_斜体文本_
	
如图所示：
![](https://i.loli.net/2020/12/29/lfJ8LicnQYmZs3W.gif)
### 粗体
	**粗体文本**
	__粗体文本__
	
如图所示：
![](https://i.loli.net/2020/12/29/SGPXUaenTh6Otzp.gif)
### 分割线
	***
	
	* * *
	
	*****
	
	- - -
	
	----------
	
如图所示：
![](https://i.loli.net/2020/12/29/e2G8kityKTuzZLb.gif)
### 删除线
	~~蔡徐坤喜欢唱跳rap~~
	
如图所示：
![](https://i.loli.net/2020/12/29/lvXIUwE7ecy94ju.gif)
### 下划线
	<u>带下划线文本</u>
	
如图所示：
![](https://i.loli.net/2020/12/29/I1ZEkzraT2gGt6q.gif)
### 脚注
```
巴拉巴拉小魔仙 <sup id="a1">[全身变](#f1)</sup>
<b id="f1">1.</b> 乌卡拉卡 [变回去↩](#a1)
```

例如：
巴拉巴拉小魔仙 <sup id="a1">[全身变](#f1)</sup>`↖点它`

------------
## 列表
	* 第一项
	+ 第二项
	- 第三项

如图所示：
![](https://i.loli.net/2021/01/06/1AVWpLMGFD73EgC.gif)

## 区块
------------
Markdown 区块引用是在段落开头使用 `>` 符号 ，然后后面紧跟一个空格符号：

	> 大家好
	> 我是蔡徐坤
	> 我不仅喜欢唱跳还喜欢rap...

区块是可以嵌套的，一个 `>` 符号是最外层，两个 `>` 符号是第一层嵌套，以此类推：

	> 大家好
	> > 我是蔡徐坤
	> > > 我不仅喜欢唱跳还喜欢rap...

如图所示：
![](https://i.loli.net/2021/01/06/wQCUydXJPlEpvSq.gif)

区块中也可使用列表：

	> 区块中使用列表
	> 1. 第一项
	> 2. 第二项
	> + 第一项
	> * 第二项
	> - 第三项

如图所示：
![](https://i.loli.net/2021/01/06/XdgU5Z8P2SbRzlF.gif)

列表中也可以使用区块：

	* 第一项
    > 大家好
    > 我是蔡徐坤
	* 第二项

如图所示：
![](https://i.loli.net/2021/01/06/MlCZWyP2zgvXpBb.gif)

## 代码
------------
如果是段落上的一个函数或片段的代码可以用反引号把它包起来`printf()`：

	`printf()` //函数
	
如图所示：
![](https://i.loli.net/2021/01/06/xEWv8oVRPwu52H7.gif)
	
### 代码块
代码区块使用 4 个`空格`或者两个制表符（`Tab` 键）或者上下文一个```：
```
$(document).ready(function () {
    alert('蔡徐坤');
});
```

如图所示：
![](https://i.loli.net/2021/01/06/ZDm6IEXfkP7aALW.gif)

## 链接
------------	
	[链接名称](链接地址)
	
	或者
	
	<链接地址>
例如：
>	链接名称 [链接地址...](https://dongjiajia.gitee.io/hexo/)

或直接使用链接地址：

>	<https://dongjiajia.gitee.io/hexo/>

### 高级链接
我们可以通过变量来设置一个链接，变量赋值在文档末尾进行：

	这个链接用 1 作为网址变量 [Google][1]
	这个链接用 runoob 作为网址变量 [Runoob][runoob]
	
然后在文档的结尾为变量赋值（网址）...

	[1]: http://www.google.com/
	[runoob]: http://www.runoob.com/
>这个链接用 1 作为网址变量 [Google][1]    
这个链接用 runoob 作为网址变量 [Runoob][runoob]

[1]: http://www.google.com/
[runoob]: http://www.runoob.com/
## 图片
------------	
	![alt 属性文本](图片地址)
	
	![alt 属性文本](图片地址 "可选标题")

例如：

![RUNOOB 图标](http://static.runoob.com/images/runoob-logo.png)

![RUNOOB 图标](http://static.runoob.com/images/runoob-logo.png "RUNOOB")

当然，也可以像网址那样对图片网址使用变量:

	这个链接用 1 作为网址变量 [RUNOOB][1].
	然后在文档的结尾为变量赋值（网址）
	
	[1]: http://static.runoob.com/images/runoob-logo.png
	
例如：

这个链接用 1 作为网址变量 [RUNOOB][1].然后在文档的结尾为变量赋值（网址）
	
	[1]: http://static.runoob.com/images/runoob-logo.png
	
### 图片高度与宽度
可以使用普通的 `<img>` 标签:

	<img src="http://static.runoob.com/images/runoob-logo.png" width="50%">
显示结果如下：

<img src="http://static.runoob.com/images/runoob-logo.png" width="50%">

## 表格
------------
Markdown 制作表格使用` | `来分隔不同的单元格，使用` - `来分隔表头和其他行:
	
	|  表头   | 表头  |
	|  ----  | ----  |
	| 单元格  | 单元格 |
	| 单元格  | 单元格 |

显示结果如下：

|  表头   | 表头  |
|  ----  | ----  |
| 单元格  | 单元格 |
| 单元格  | 单元格 |

### 对齐方式
* `-:` 设置内容和标题栏居右对齐。
* `:-` 设置内容和标题栏居左对齐。
* `:-:` 设置内容和标题栏居中对齐。


	| 左对齐 | 右对齐 | 居中对齐 |
	| :---- | -----: | :-----: |
	| 单元格 | 单元格 | 单元格 |
	| 单元格 | 单元格 | 单元格 |
	
显示结果如下（存在兼容性问题）：

| 左对齐 | 右对齐 | 居中对齐 |
| :-----| ----: | :----: |
| 单元格 | 单元格 | 单元格 |
| 单元格 | 单元格 | 单元格 |
	
## 高级技巧
------------
### 键盘指令
	使用 <kbd>Ctrl</kbd>+<kbd>Alt</kbd>+<kbd>Del</kbd> 重启电脑
>使用 <kbd>Ctrl</kbd>+<kbd>Alt</kbd>+<kbd>Del</kbd> 重启电脑
### 转义
符号前面加上`\`（反斜杠）来帮助插入普通的符号:
	
	**文本加粗**
	\*\* 正常显示星号 \*\*
>**文本加粗**<br>
\*\* 正常显示星号 \*\*

	\   反斜线
	`   反引号
	*   星号
	_   下划线
	{}  花括号
	[]  方括号
	()  小括号
	#   井字号
	+   加号
	-   减号
	.   英文句点
	!   感叹号

## MarkDown在线编辑网站推荐
[Markdown|让排版变Nice](https://www.mdnice.com/)
[Markdown在线编辑器-MdEditor](http://www.mdeditor.com/)
----------
<b id="f1">脚注：</b> 乌卡拉卡 [变回去↩](#a1)


	