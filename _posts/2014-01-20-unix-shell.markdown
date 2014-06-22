---
layout: post
title:  "Unix Shell"
date:   2014-01-20 22:33:00
categories: shell
img_src: "/img/linux.jpg"
description: "Linux 脚本编写基础"
---
<p style="margin-top:0px; margin-bottom:0px; padding-top:0px; padding-bottom:0px; font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">
	<strong>1. Linux 脚本编写基础<br />
	1.1 语法基本介绍<br />
	1.1.1 开头</strong><br />
	程序必须以下面的行开始（必须方在文件的第一行）：<br />
	
</p>
<div class="code_main" style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left; color:rgb(102,102,102); padding-top:4px; padding-right:4px; padding-bottom:4px; padding-left:4px; margin-top:2px; margin-right:2px; margin-bottom:2px; margin-left:2px; border-top-width:1px; border-right-width:1px; border-bottom-width:1px; border-left-width:1px; border-top-style:dashed; border-right-style:dashed; border-bottom-style:dashed; border-left-style:dashed; border-top-color:rgb(102,102,102); border-right-color:rgb(102,102,102); border-bottom-color:rgb(102,102,102); border-left-color:rgb(102,102,102)">
	#!/bin/sh
</div>
<br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">　　符号#!用来告诉系统它后面的参数是用来执行该文件的程序。在这个例子中我们使用/bin/sh来执行程序。</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">　　当编辑好脚本时，如果要执行该脚本，还必须使其可执行。</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">　　要使脚本可执行：</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left; color:red">编译 chmod +x filename 这样才能用./filename 来运行</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">1.1.2 注释</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">　　在进行shell编程时，以#开头的句子表示注释，直到这一行的结束。我们真诚地建议您在程序中使用注释。</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">　　如果您使用了注释，那么即使相当长的时间内没有使用该脚本，您也能在很短的时间内明白该脚本的作用及工作原理。</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">1.1.3 变量</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">　　在其他编程语言中您必须使用变量。在shell编程中，所有的变量都由字符串组成，并且您不需要对变量进行声明。要赋值给一个变量，您可以这样写：</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />

<div class="code_main" style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left; color:rgb(102,102,102); padding-top:4px; padding-right:4px; padding-bottom:4px; padding-left:4px; margin-top:2px; margin-right:2px; margin-bottom:2px; margin-left:2px; border-top-width:1px; border-right-width:1px; border-bottom-width:1px; border-left-width:1px; border-top-style:dashed; border-right-style:dashed; border-bottom-style:dashed; border-left-style:dashed; border-top-color:rgb(102,102,102); border-right-color:rgb(102,102,102); border-bottom-color:rgb(102,102,102); border-left-color:rgb(102,102,102)">
	#!/bin/sh
</div>
<br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">#对变量赋值：</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />

<div class="code_main" style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left; color:rgb(102,102,102); padding-top:4px; padding-right:4px; padding-bottom:4px; padding-left:4px; margin-top:2px; margin-right:2px; margin-bottom:2px; margin-left:2px; border-top-width:1px; border-right-width:1px; border-bottom-width:1px; border-left-width:1px; border-top-style:dashed; border-right-style:dashed; border-bottom-style:dashed; border-left-style:dashed; border-top-color:rgb(102,102,102); border-right-color:rgb(102,102,102); border-bottom-color:rgb(102,102,102); border-left-color:rgb(102,102,102)">
	a=&quot;hello world&quot;<br />
	# 现在打印变量a的内容：<br />
	echo &quot;A is:&quot;<br />
	echo $a
</div>
<br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">有时候变量名很容易与其他文字混淆，比如：</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />

<div class="code_main" style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left; color:rgb(102,102,102); padding-top:4px; padding-right:4px; padding-bottom:4px; padding-left:4px; margin-top:2px; margin-right:2px; margin-bottom:2px; margin-left:2px; border-top-width:1px; border-right-width:1px; border-bottom-width:1px; border-left-width:1px; border-top-style:dashed; border-right-style:dashed; border-bottom-style:dashed; border-left-style:dashed; border-top-color:rgb(102,102,102); border-right-color:rgb(102,102,102); border-bottom-color:rgb(102,102,102); border-left-color:rgb(102,102,102)">
	num=2<br />
	echo &quot;this is the $numnd&quot;
</div>
<br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">这并不会打印出&quot;this is the 2nd&quot;，而仅仅打印&quot;this is the &quot;，因为shell会去搜索变量numnd的值，但是这个变量时没有值的。可以使用花括号来告诉shell我们要打印的是num变量：</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />

<div class="code_main" style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left; color:rgb(102,102,102); padding-top:4px; padding-right:4px; padding-bottom:4px; padding-left:4px; margin-top:2px; margin-right:2px; margin-bottom:2px; margin-left:2px; border-top-width:1px; border-right-width:1px; border-bottom-width:1px; border-left-width:1px; border-top-style:dashed; border-right-style:dashed; border-bottom-style:dashed; border-left-style:dashed; border-top-color:rgb(102,102,102); border-right-color:rgb(102,102,102); border-bottom-color:rgb(102,102,102); border-left-color:rgb(102,102,102)">
	num=2<br />
	echo &quot;this is the ${num}nd&quot;
</div>
<br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">　　这将打印： </span><span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left"></span>
<div class="code_main" style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left; color:rgb(102,102,102); padding-top:4px; padding-right:4px; padding-bottom:4px; padding-left:4px; margin-top:2px; margin-right:2px; margin-bottom:2px; margin-left:2px; border-top-width:1px; border-right-width:1px; border-bottom-width:1px; border-left-width:1px; border-top-style:dashed; border-right-style:dashed; border-bottom-style:dashed; border-left-style:dashed; border-top-color:rgb(102,102,102); border-right-color:rgb(102,102,102); border-bottom-color:rgb(102,102,102); border-left-color:rgb(102,102,102)">
	this is the 2nd
</div>
<br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">1.1.4 环境变量</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">由export关键字处理过的变量叫做环境变量。我们不对环境变量进行讨论，因为通常情况下仅仅在登录脚本中使用环境变量。</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">1.1.5 Shell命令和流程控制</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">在shell脚本中可以使用三类命令：</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">1)Unix 命令:</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">　　虽然在shell脚本中可以使用任意的unix命令，但是还是由一些相对更常用的命令。这些命令通常是用来进行文件和文字操作的。</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">常用命令语法及功能</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">　　echo &quot;some text&quot;: 将文字内容打印在屏幕上</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">　　ls: 文件列表</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">　　wc –l filewc -w filewc -c file: 计算文件行数计算文件中的单词数计算文件中的字符数</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">　　cp sourcefile destfile: 文件拷贝</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">　　mv oldname newname : 重命名文件或移动文件</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">　　rm file: 删除文件</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">　　grep 'pattern' file: 在文件内搜索字符串比如：grep 'searchstring' file.txt</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">　　cut -b colnum file: 指定欲显示的文件内容范围，并将它们输出到标准输出设备比如：输出每行第5个到第9个字符cut -b5-9 file.txt千万不要和cat命令混淆，</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">这是两个完全不同的命令</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">　　cat file.txt: 输出文件内容到标准输出设备（屏幕）上</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">　　file somefile: 得到文件类型</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">　　read var: 提示用户输入，并将输入赋值给变量</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">　　sort file.txt: 对file.txt文件中的行进行排序</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">　　uniq: 删除文本文件中出现的行列比如： sort file.txt | uniq</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">　　expr: 进行数学运算Example: add 2 and 3expr 2 &quot;+&quot; 3</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">　　find: 搜索文件比如：根据文件名搜索find . -name filename -print</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">　　tee: 将数据输出到标准输出设备(屏幕) 和文件比如：somecommand | tee outfile</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">　　basename file: 返回不包含路径的文件名比如： basename /bin/tux将返回 tux</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">　　dirname file: 返回文件所在路径比如：dirname /bin/tux将返回 /bin</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">　　head file: 打印文本文件开头几行</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">　　tail file : 打印文本文件末尾几行</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">　　sed: Sed是一个基本的查找替换程序。可以从标准输入（比如命令管道）读入文本，并将</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">结果输出到标准输出（屏幕）。该命令采用正则表达式（见参考）进行搜索。不要和shell中的通配符相混淆。比如：将linuxfocus 替换为LinuxFocus ：</span><span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left"></span>
<div class="code_main" style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left; color:rgb(102,102,102); padding-top:4px; padding-right:4px; padding-bottom:4px; padding-left:4px; margin-top:2px; margin-right:2px; margin-bottom:2px; margin-left:2px; border-top-width:1px; border-right-width:1px; border-bottom-width:1px; border-left-width:1px; border-top-style:dashed; border-right-style:dashed; border-bottom-style:dashed; border-left-style:dashed; border-top-color:rgb(102,102,102); border-right-color:rgb(102,102,102); border-bottom-color:rgb(102,102,102); border-left-color:rgb(102,102,102)">
	cat text.file | sed 's/linuxfocus/LinuxFocus/' &gt; newtext.file
</div>
<br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">　　awk: awk 用来从文本文件中提取字段。缺省地，字段分割符是空格，可以使用-F指定其他分割符。</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />

<div class="code_main" style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left; color:rgb(102,102,102); padding-top:4px; padding-right:4px; padding-bottom:4px; padding-left:4px; margin-top:2px; margin-right:2px; margin-bottom:2px; margin-left:2px; border-top-width:1px; border-right-width:1px; border-bottom-width:1px; border-left-width:1px; border-top-style:dashed; border-right-style:dashed; border-bottom-style:dashed; border-left-style:dashed; border-top-color:rgb(102,102,102); border-right-color:rgb(102,102,102); border-bottom-color:rgb(102,102,102); border-left-color:rgb(102,102,102)">
	cat file.txt | awk -F, '{print $1 &quot;,&quot; $3 }'
</div>
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">这里我们使用，作为字段分割符，同时打印第一个和第三个字段。如果该文件内容如下： Adam Bor, 34, IndiaKerry Miller, 22, USA命令输出结果为：Adam Bor, IndiaKerry Miller, USA</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">2) 概念: 管道, 重定向和 backtick</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">　　这些不是系统命令，但是他们真的很重要。</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">　　</span><span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">管道 (|) </span><span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">将一个命令的输出作为另外一个命令的输入。</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />

<div class="code_main" style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left; color:rgb(102,102,102); padding-top:4px; padding-right:4px; padding-bottom:4px; padding-left:4px; margin-top:2px; margin-right:2px; margin-bottom:2px; margin-left:2px; border-top-width:1px; border-right-width:1px; border-bottom-width:1px; border-left-width:1px; border-top-style:dashed; border-right-style:dashed; border-bottom-style:dashed; border-left-style:dashed; border-top-color:rgb(102,102,102); border-right-color:rgb(102,102,102); border-bottom-color:rgb(102,102,102); border-left-color:rgb(102,102,102)">
	grep &quot;hello&quot; file.txt | wc -l
</div>
<br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">　　在file.txt中搜索包含有”hello”的行并计算其行数。</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">　　在这里grep命令的输出作为wc命令的输入。当然您可以使用多个命令。</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">　　重定向：将命令的结果输出到文件，而不是标准输出（屏幕）。</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">　　</span><span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">&gt;</span><span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left"> 写入文件并覆盖旧文件</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">　　</span><span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">&gt;&gt; </span><span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">加到文件的尾部，保留旧文件内容。</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">反短斜线</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">　使用反短斜线可以将一个命令的输出作为另外一个命令的一个命令行参数。</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">命令：</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />

<div class="code_main" style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left; color:rgb(102,102,102); padding-top:4px; padding-right:4px; padding-bottom:4px; padding-left:4px; margin-top:2px; margin-right:2px; margin-bottom:2px; margin-left:2px; border-top-width:1px; border-right-width:1px; border-bottom-width:1px; border-left-width:1px; border-top-style:dashed; border-right-style:dashed; border-bottom-style:dashed; border-left-style:dashed; border-top-color:rgb(102,102,102); border-right-color:rgb(102,102,102); border-bottom-color:rgb(102,102,102); border-left-color:rgb(102,102,102)">
	find . -mtime -1 -type f -print
</div>
<br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">　　用来查找过去24小时（-mtime –2则表示过去48小时）内修改过的文件。如果您想将所有查找到的文件打一个包，则可以使用以下脚本：</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />

<div class="code_main" style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left; color:rgb(102,102,102); padding-top:4px; padding-right:4px; padding-bottom:4px; padding-left:4px; margin-top:2px; margin-right:2px; margin-bottom:2px; margin-left:2px; border-top-width:1px; border-right-width:1px; border-bottom-width:1px; border-left-width:1px; border-top-style:dashed; border-right-style:dashed; border-bottom-style:dashed; border-left-style:dashed; border-top-color:rgb(102,102,102); border-right-color:rgb(102,102,102); border-bottom-color:rgb(102,102,102); border-left-color:rgb(102,102,102)">
	#!/bin/sh<br />
	# The ticks are backticks (`) not normal quotes ('):<br />
	tar -zcvf lastmod.tar.gz `find . -mtime -1 -type f -print`
</div>
<br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">3) 流程控制</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">1.if</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">　　&quot;if&quot; 表达式 如果条件为真则执行then后面的部分：</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />

<div class="code_main" style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left; color:rgb(102,102,102); padding-top:4px; padding-right:4px; padding-bottom:4px; padding-left:4px; margin-top:2px; margin-right:2px; margin-bottom:2px; margin-left:2px; border-top-width:1px; border-right-width:1px; border-bottom-width:1px; border-left-width:1px; border-top-style:dashed; border-right-style:dashed; border-bottom-style:dashed; border-left-style:dashed; border-top-color:rgb(102,102,102); border-right-color:rgb(102,102,102); border-bottom-color:rgb(102,102,102); border-left-color:rgb(102,102,102)">
	if ....; then<br />
	　 ....<br />
	elif ....; then<br />
	　 ....<br />
	else<br />
	　 ....<br />
	fi
</div>
<br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">大多数情况下，可以使用测试命令来对条件进行测试。比如可以比较字符串、判断文件是否存在及是否可读等等…</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">　　通常用&quot; [ ] &quot;来表示条件测试。注意这里的空格很重要。要确保方括号的空格。</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">[ -f &quot;somefile&quot; ] ：判断是否是一个文件</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">[ -x &quot;/bin/ls&quot; ] ：判断/bin/ls是否存在并有可执行权限</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">[ -n &quot;$var&quot; ] ：判断$var变量是否有值</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">[ &quot;$a&quot; = &quot;$b&quot; ] ：判断$a和$b是否相等</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">　　执行man test可以查看所有测试表达式可以比较和判断的类型。</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">　　直接执行以下脚本：</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />

<div class="code_main" style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left; color:rgb(102,102,102); padding-top:4px; padding-right:4px; padding-bottom:4px; padding-left:4px; margin-top:2px; margin-right:2px; margin-bottom:2px; margin-left:2px; border-top-width:1px; border-right-width:1px; border-bottom-width:1px; border-left-width:1px; border-top-style:dashed; border-right-style:dashed; border-bottom-style:dashed; border-left-style:dashed; border-top-color:rgb(102,102,102); border-right-color:rgb(102,102,102); border-bottom-color:rgb(102,102,102); border-left-color:rgb(102,102,102)">
	#!/bin/sh<br />
	if [ &quot;$SHELL&quot; = &quot;/bin/bash&quot; ]; then<br />
	　echo &quot;your login shell is the bash (bourne again shell)&quot;<br />
	else<br />
	　echo &quot;your login shell is not bash but $SHELL&quot;<br />
	fi
</div>
<br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">　　变量$SHELL包含了登录shell的名称，我们和/bin/bash进行了比较。</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">快捷操作符</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">熟悉C语言的朋友可能会很喜欢下面的表达式：</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />

<div class="code_main" style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left; color:rgb(102,102,102); padding-top:4px; padding-right:4px; padding-bottom:4px; padding-left:4px; margin-top:2px; margin-right:2px; margin-bottom:2px; margin-left:2px; border-top-width:1px; border-right-width:1px; border-bottom-width:1px; border-left-width:1px; border-top-style:dashed; border-right-style:dashed; border-bottom-style:dashed; border-left-style:dashed; border-top-color:rgb(102,102,102); border-right-color:rgb(102,102,102); border-bottom-color:rgb(102,102,102); border-left-color:rgb(102,102,102)">
	[ -f &quot;/etc/shadow&quot; ] &amp;&amp; echo &quot;This computer uses shadow passwors&quot;
</div>
<br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">　　这里 &amp;&amp; 就是一个快捷操作符，如果左边的表达式为真则执行右边的语句。</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">您也可以认为是逻辑运算中的与操作。上例中表示如果/etc/shadow文件存在则打印” This computer uses shadow passwors”。同样或操作(||)在shell编程中也是可用的。这里有个例子：</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />

<div class="code_main" style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left; color:rgb(102,102,102); padding-top:4px; padding-right:4px; padding-bottom:4px; padding-left:4px; margin-top:2px; margin-right:2px; margin-bottom:2px; margin-left:2px; border-top-width:1px; border-right-width:1px; border-bottom-width:1px; border-left-width:1px; border-top-style:dashed; border-right-style:dashed; border-bottom-style:dashed; border-left-style:dashed; border-top-color:rgb(102,102,102); border-right-color:rgb(102,102,102); border-bottom-color:rgb(102,102,102); border-left-color:rgb(102,102,102)">
	#!/bin/sh<br />
	mailfolder=/var/spool/mail/james<br />
	[ -r &quot;$mailfolder&quot; ]<br />
	'  '{ echo &quot;Can not read $mailfolder&quot; ; exit 1; }<br />
	echo &quot;$mailfolder has mail from:&quot;<br />
	grep &quot;^From &quot; $mailfolder
</div>
<br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">该脚本首先判断mailfolder是否可读。如果可读则打印该文件中的&quot;From&quot; 一行。如果不可读则或操作生效，打印错误信息后脚本退出。这里有个问题，那就是我们必须有两个命令：</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">　　-打印错误信息</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">　　-退出程序</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">　　我们使用花括号以匿名函数的形式将两个命令放到一起作为一个命令使用。一般函数将在下文提及。</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">　　不用与和或操作符，我们也可以用if表达式作任何事情，但是使用与或操作符会更便利很多。</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">2.case</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">case :表达式可以用来匹配一个给定的字符串，而不是数字。</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />

<div class="code_main" style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left; color:rgb(102,102,102); padding-top:4px; padding-right:4px; padding-bottom:4px; padding-left:4px; margin-top:2px; margin-right:2px; margin-bottom:2px; margin-left:2px; border-top-width:1px; border-right-width:1px; border-bottom-width:1px; border-left-width:1px; border-top-style:dashed; border-right-style:dashed; border-bottom-style:dashed; border-left-style:dashed; border-top-color:rgb(102,102,102); border-right-color:rgb(102,102,102); border-bottom-color:rgb(102,102,102); border-left-color:rgb(102,102,102)">
	case ... in<br />
	...) do something here ;;<br />
	esac
</div>
<br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">　　让我们看一个例子。 file命令可以辨别出一个给定文件的文件类型，比如：</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />

<div class="code_main" style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left; color:rgb(102,102,102); padding-top:4px; padding-right:4px; padding-bottom:4px; padding-left:4px; margin-top:2px; margin-right:2px; margin-bottom:2px; margin-left:2px; border-top-width:1px; border-right-width:1px; border-bottom-width:1px; border-left-width:1px; border-top-style:dashed; border-right-style:dashed; border-bottom-style:dashed; border-left-style:dashed; border-top-color:rgb(102,102,102); border-right-color:rgb(102,102,102); border-bottom-color:rgb(102,102,102); border-left-color:rgb(102,102,102)">
	file lf.gz
</div>
<br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">　　这将返回：</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />

<div class="code_main" style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left; color:rgb(102,102,102); padding-top:4px; padding-right:4px; padding-bottom:4px; padding-left:4px; margin-top:2px; margin-right:2px; margin-bottom:2px; margin-left:2px; border-top-width:1px; border-right-width:1px; border-bottom-width:1px; border-left-width:1px; border-top-style:dashed; border-right-style:dashed; border-bottom-style:dashed; border-left-style:dashed; border-top-color:rgb(102,102,102); border-right-color:rgb(102,102,102); border-bottom-color:rgb(102,102,102); border-left-color:rgb(102,102,102)">
	lf.gz: gzip compressed data, deflated, original filename,<br />
	last modified: Mon Aug 27 23:09:18 2001, os: Unix
</div>
<br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">　我们利用这一点写了一个叫做smartzip的脚本，该脚本可以自动解压bzip2, gzip 和zip 类型的压缩文件：</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />

<div class="code_main" style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left; color:rgb(102,102,102); padding-top:4px; padding-right:4px; padding-bottom:4px; padding-left:4px; margin-top:2px; margin-right:2px; margin-bottom:2px; margin-left:2px; border-top-width:1px; border-right-width:1px; border-bottom-width:1px; border-left-width:1px; border-top-style:dashed; border-right-style:dashed; border-bottom-style:dashed; border-left-style:dashed; border-top-color:rgb(102,102,102); border-right-color:rgb(102,102,102); border-bottom-color:rgb(102,102,102); border-left-color:rgb(102,102,102)">
	#!/bin/sh<br />
	ftype=`file &quot;$1&quot;`<br />
	case &quot;$ftype&quot; in<br />
	&quot;$1: Zip archive&quot;*)<br />
	　　unzip &quot;$1&quot; ;;<br />
	&quot;$1: gzip compressed&quot;*)<br />
	　　gunzip &quot;$1&quot; ;;<br />
	&quot;$1: bzip2 compressed&quot;*)<br />
	　　bunzip2 &quot;$1&quot; ;;<br />
	*) echo &quot;File $1 can not be uncompressed with smartzip&quot;;;<br />
	esac
</div>
<br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">　　您可能注意到我们在这里使用了一个特殊的变量$1。该变量包含了传递给该程序的第一个参数值。</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">也就是说，当我们运行：</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />

<div class="code_main" style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left; color:rgb(102,102,102); padding-top:4px; padding-right:4px; padding-bottom:4px; padding-left:4px; margin-top:2px; margin-right:2px; margin-bottom:2px; margin-left:2px; border-top-width:1px; border-right-width:1px; border-bottom-width:1px; border-left-width:1px; border-top-style:dashed; border-right-style:dashed; border-bottom-style:dashed; border-left-style:dashed; border-top-color:rgb(102,102,102); border-right-color:rgb(102,102,102); border-bottom-color:rgb(102,102,102); border-left-color:rgb(102,102,102)">
	smartzip articles.zip
</div>
<br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">$1 就是字符串 articles.zip</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">3. selsect</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">select 表达式是一种bash的扩展应用，尤其擅长于交互式使用。用户可以从一组不同的值中进行选择。</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />

<div class="code_main" style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left; color:rgb(102,102,102); padding-top:4px; padding-right:4px; padding-bottom:4px; padding-left:4px; margin-top:2px; margin-right:2px; margin-bottom:2px; margin-left:2px; border-top-width:1px; border-right-width:1px; border-bottom-width:1px; border-left-width:1px; border-top-style:dashed; border-right-style:dashed; border-bottom-style:dashed; border-left-style:dashed; border-top-color:rgb(102,102,102); border-right-color:rgb(102,102,102); border-bottom-color:rgb(102,102,102); border-left-color:rgb(102,102,102)">
	select var in ... ; do<br />
	　break<br />
	done<br />
	.... now $var can be used ....
</div>
<br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">下面是一个例子：</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />

<div class="code_main" style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left; color:rgb(102,102,102); padding-top:4px; padding-right:4px; padding-bottom:4px; padding-left:4px; margin-top:2px; margin-right:2px; margin-bottom:2px; margin-left:2px; border-top-width:1px; border-right-width:1px; border-bottom-width:1px; border-left-width:1px; border-top-style:dashed; border-right-style:dashed; border-bottom-style:dashed; border-left-style:dashed; border-top-color:rgb(102,102,102); border-right-color:rgb(102,102,102); border-bottom-color:rgb(102,102,102); border-left-color:rgb(102,102,102)">
	#!/bin/sh<br />
	echo &quot;What is your favourite OS?&quot;<br />
	select var in &quot;Linux&quot; &quot;Gnu Hurd&quot; &quot;Free BSD&quot; &quot;Other&quot;; do<br />
	　　　　break<br />
	done<br />
	echo &quot;You have selected $var&quot;
</div>
<br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">　　下面是该脚本运行的结果：</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />

<div class="code_main" style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left; color:rgb(102,102,102); padding-top:4px; padding-right:4px; padding-bottom:4px; padding-left:4px; margin-top:2px; margin-right:2px; margin-bottom:2px; margin-left:2px; border-top-width:1px; border-right-width:1px; border-bottom-width:1px; border-left-width:1px; border-top-style:dashed; border-right-style:dashed; border-bottom-style:dashed; border-left-style:dashed; border-top-color:rgb(102,102,102); border-right-color:rgb(102,102,102); border-bottom-color:rgb(102,102,102); border-left-color:rgb(102,102,102)">
	What is your favourite OS?<br />
	1) Linux<br />
	2) Gnu Hurd<br />
	3) Free BSD<br />
	4) Other<br />
	#? 1<br />
	You have selected Linux
</div>
<br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">4.loop</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">loop表达式：</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />

<div class="code_main" style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left; color:rgb(102,102,102); padding-top:4px; padding-right:4px; padding-bottom:4px; padding-left:4px; margin-top:2px; margin-right:2px; margin-bottom:2px; margin-left:2px; border-top-width:1px; border-right-width:1px; border-bottom-width:1px; border-left-width:1px; border-top-style:dashed; border-right-style:dashed; border-bottom-style:dashed; border-left-style:dashed; border-top-color:rgb(102,102,102); border-right-color:rgb(102,102,102); border-bottom-color:rgb(102,102,102); border-left-color:rgb(102,102,102)">
	while ...; do<br />
	....<br />
	done
</div>
<br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">　　</span><span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">while-loop </span><span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">将运行直到表达式测试为真。will run while the expression that we test for is true.</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">关键字&quot;break&quot; 用来跳出循环。而关键字”continue”用来不执行余下的部分而直接跳到下一个循环。</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">　　</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">for-loop</span><span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">表达式查看一个字符串列表 (字符串用空格分隔) 然后将其赋给一个变量：</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />

<div class="code_main" style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left; color:rgb(102,102,102); padding-top:4px; padding-right:4px; padding-bottom:4px; padding-left:4px; margin-top:2px; margin-right:2px; margin-bottom:2px; margin-left:2px; border-top-width:1px; border-right-width:1px; border-bottom-width:1px; border-left-width:1px; border-top-style:dashed; border-right-style:dashed; border-bottom-style:dashed; border-left-style:dashed; border-top-color:rgb(102,102,102); border-right-color:rgb(102,102,102); border-bottom-color:rgb(102,102,102); border-left-color:rgb(102,102,102)">
	for var in ....; do<br />
	　 ....<br />
	done
</div>
<br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">在下面的例子中，将分别打印ABC到屏幕上：</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />

<div class="code_main" style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left; color:rgb(102,102,102); padding-top:4px; padding-right:4px; padding-bottom:4px; padding-left:4px; margin-top:2px; margin-right:2px; margin-bottom:2px; margin-left:2px; border-top-width:1px; border-right-width:1px; border-bottom-width:1px; border-left-width:1px; border-top-style:dashed; border-right-style:dashed; border-bottom-style:dashed; border-left-style:dashed; border-top-color:rgb(102,102,102); border-right-color:rgb(102,102,102); border-bottom-color:rgb(102,102,102); border-left-color:rgb(102,102,102)">
	#!/bin/sh<br />
	for var in A B C ; do<br />
	　 echo &quot;var is $var&quot;<br />
	done
</div>
<br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">下面是一个更为有用的脚本showrpm，其功能是打印一些RPM包的统计信息：</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />

<div class="code_main" style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left; color:rgb(102,102,102); padding-top:4px; padding-right:4px; padding-bottom:4px; padding-left:4px; margin-top:2px; margin-right:2px; margin-bottom:2px; margin-left:2px; border-top-width:1px; border-right-width:1px; border-bottom-width:1px; border-left-width:1px; border-top-style:dashed; border-right-style:dashed; border-bottom-style:dashed; border-left-style:dashed; border-top-color:rgb(102,102,102); border-right-color:rgb(102,102,102); border-bottom-color:rgb(102,102,102); border-left-color:rgb(102,102,102)">
	#!/bin/sh<br />
	# list a content summary of a number of RPM packages<br />
	# USAGE: showrpm rpmfile1 rpmfile2 ...<br />
	# EXAMPLE: showrpm /cdrom/RedHat/RPMS/*.rpm<br />
	for rpmpackage in $*; do<br />
	　if [ -r &quot;$rpmpackage&quot; ];then<br />
	　　echo &quot;=============== $rpmpackage ==============&quot;<br />
	　　rpm -qi -p $rpmpackage<br />
	　else<br />
	　　echo &quot;ERROR: cannot read file $rpmpackage&quot;<br />
	　fi<br />
	done
</div>
<br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">　　这里出现了第二个特殊的变量$*，该变量包含了所有输入的命令行参数值。</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">如果您运行showrpm openssh.rpm w3m.rpm webgrep.rpm</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">此时 $* 包含了 3 个字符串，即openssh.rpm, w3m.rpm and webgrep.rpm.</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">5. 引号</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">在向程序传递任何参数之前，程序会扩展通配符和变量。这里所谓扩展的意思是程序会把通配符（比如*）替换成合适的文件名，它变量替换成变量值。为了防止程序作这种替换，您可以使用引号：让我们来看一个例子，假设在当前目录下有一些文件，两个jpg文件， mail.jpg 和tux.jpg。</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />

<div class="code_main" style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left; color:rgb(102,102,102); padding-top:4px; padding-right:4px; padding-bottom:4px; padding-left:4px; margin-top:2px; margin-right:2px; margin-bottom:2px; margin-left:2px; border-top-width:1px; border-right-width:1px; border-bottom-width:1px; border-left-width:1px; border-top-style:dashed; border-right-style:dashed; border-bottom-style:dashed; border-left-style:dashed; border-top-color:rgb(102,102,102); border-right-color:rgb(102,102,102); border-bottom-color:rgb(102,102,102); border-left-color:rgb(102,102,102)">
	#!/bin/sh<br />
	echo *.jpg
</div>
<br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">　　这将打印出&quot;mail.jpg tux.jpg&quot;的结果。</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">　　引号 (单引号和双引号) 将防止这种通配符扩展：</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />

<div class="code_main" style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left; color:rgb(102,102,102); padding-top:4px; padding-right:4px; padding-bottom:4px; padding-left:4px; margin-top:2px; margin-right:2px; margin-bottom:2px; margin-left:2px; border-top-width:1px; border-right-width:1px; border-bottom-width:1px; border-left-width:1px; border-top-style:dashed; border-right-style:dashed; border-bottom-style:dashed; border-left-style:dashed; border-top-color:rgb(102,102,102); border-right-color:rgb(102,102,102); border-bottom-color:rgb(102,102,102); border-left-color:rgb(102,102,102)">
	#!/bin/sh<br />
	echo &quot;*.jpg&quot;<br />
	echo '*.jpg'
</div>
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">　　这将打印&quot;*.jpg&quot; 两次。</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">　　单引号更严格一些。它可以防止任何变量扩展。双引号可以防止通配符扩展但允许变量扩展。</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />

<div class="code_main" style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left; color:rgb(102,102,102); padding-top:4px; padding-right:4px; padding-bottom:4px; padding-left:4px; margin-top:2px; margin-right:2px; margin-bottom:2px; margin-left:2px; border-top-width:1px; border-right-width:1px; border-bottom-width:1px; border-left-width:1px; border-top-style:dashed; border-right-style:dashed; border-bottom-style:dashed; border-left-style:dashed; border-top-color:rgb(102,102,102); border-right-color:rgb(102,102,102); border-bottom-color:rgb(102,102,102); border-left-color:rgb(102,102,102)">
	#!/bin/sh<br />
	echo $SHELL<br />
	echo &quot;$SHELL&quot;<br />
	echo '$SHELL'
</div>
<br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">　　运行结果为：</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />

<div class="code_main" style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left; color:rgb(102,102,102); padding-top:4px; padding-right:4px; padding-bottom:4px; padding-left:4px; margin-top:2px; margin-right:2px; margin-bottom:2px; margin-left:2px; border-top-width:1px; border-right-width:1px; border-bottom-width:1px; border-left-width:1px; border-top-style:dashed; border-right-style:dashed; border-bottom-style:dashed; border-left-style:dashed; border-top-color:rgb(102,102,102); border-right-color:rgb(102,102,102); border-bottom-color:rgb(102,102,102); border-left-color:rgb(102,102,102)">
	/bin/bash<br />
	/bin/bash<br />
	$SHELL
</div>
<br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">　　最后，还有一种防止这种扩展的方法，那就是使用转义字符——反斜杠：</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />

<div class="code_main" style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left; color:rgb(102,102,102); padding-top:4px; padding-right:4px; padding-bottom:4px; padding-left:4px; margin-top:2px; margin-right:2px; margin-bottom:2px; margin-left:2px; border-top-width:1px; border-right-width:1px; border-bottom-width:1px; border-left-width:1px; border-top-style:dashed; border-right-style:dashed; border-bottom-style:dashed; border-left-style:dashed; border-top-color:rgb(102,102,102); border-right-color:rgb(102,102,102); border-bottom-color:rgb(102,102,102); border-left-color:rgb(102,102,102)">
	echo *.jpg<br />
	echo $SHELL
</div>
<br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">　　这将输出：</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />

<div class="code_main" style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left; color:rgb(102,102,102); padding-top:4px; padding-right:4px; padding-bottom:4px; padding-left:4px; margin-top:2px; margin-right:2px; margin-bottom:2px; margin-left:2px; border-top-width:1px; border-right-width:1px; border-bottom-width:1px; border-left-width:1px; border-top-style:dashed; border-right-style:dashed; border-bottom-style:dashed; border-left-style:dashed; border-top-color:rgb(102,102,102); border-right-color:rgb(102,102,102); border-bottom-color:rgb(102,102,102); border-left-color:rgb(102,102,102)">
	*.jpg<br />
	$SHELL
</div>
<br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">6. Here documents</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">当要将几行文字传递给一个命令时，here documents（译者注：目前还没有见到过对该词适合的翻译）一种不错的方法。对每个脚本写一段帮助性的文字是很有用的，此时如果我们四有那个 here documents就不必用echo函数一行行输出。 一个 &quot;Here document&quot; 以 &lt;&lt; 开头，后面接上一个字符串，这个字符串还必须出现在here document的末尾。下面是一个例子，在该例子中，我们对多个文件进行重命名，并且使用here documents打印帮助：</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />

<div class="code_main" style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left; color:rgb(102,102,102); padding-top:4px; padding-right:4px; padding-bottom:4px; padding-left:4px; margin-top:2px; margin-right:2px; margin-bottom:2px; margin-left:2px; border-top-width:1px; border-right-width:1px; border-bottom-width:1px; border-left-width:1px; border-top-style:dashed; border-right-style:dashed; border-bottom-style:dashed; border-left-style:dashed; border-top-color:rgb(102,102,102); border-right-color:rgb(102,102,102); border-bottom-color:rgb(102,102,102); border-left-color:rgb(102,102,102)">
	#!/bin/sh<br />
	# we have less than 3 arguments. Print the help text:<br />
	if [ $# -lt 3 ] ; then<br />
	cat &lt;<br />
	ren -- renames a number of files using sed regular expressions<br />
	USAGE: ren 'regexp' 'replacement' files...<br />
	EXAMPLE: rename all *.HTM files in *.html:<br />
	　ren 'HTM$' 'html' *.HTM<br />
	HELP<br />
	　exit 0<br />
	fi<br />
	OLD=&quot;$1&quot;<br />
	NEW=&quot;$2&quot;<br />
	# The shift command removes one argument from the list of<br />
	# command line arguments.<br />
	shift<br />
	shift<br />
	# $* contains now all the files:<br />
	for file in $*; do<br />
	　　if [ -f &quot;$file&quot; ] ; then<br />
	　　　newfile=`echo &quot;$file&quot; | sed &quot;s/${OLD}/${NEW}/g&quot;`<br />
	　　　if [ -f &quot;$newfile&quot; ]; then<br />
	　　　　echo &quot;ERROR: $newfile exists already&quot;<br />
	　　　else<br />
	　　　　echo &quot;renaming $file to $newfile ...&quot;<br />
	　　　　mv &quot;$file&quot; &quot;$newfile&quot;<br />
	　　　fi<br />
	　　fi<br />
	done
</div>
<br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">　这是一个复杂一些的例子。让我们详细讨论一下。第一个if表达式判断输入命令行参数是否小于3个 (特殊变量$# 表示包含参数的个数) 。如果输入参数小于3个，则将帮助文字传递给cat命令，然后由cat命令将其打印在屏幕上。打印帮助文字后程序退出。如果输入参数等于或大于3个，我们就将第一个参数赋值给变量OLD，第二个参数赋值给变量NEW。下一步，我们使用shift命令将第一个和第二个参数从参数列表中删除，这样原来的第三个参数就成为参数列表$*的第一个参数。然后我们开始循环，命令行参数列表被一个接一个地被赋值给变量$file。接着我们判断该文件是否存在，如果存在则通过sed命令搜索和替换来产生新的文件名。然后将反短斜线内命令结果赋值给newfile。这样我们就达到了我们的目的：得到了旧文件名和新文件名。然后使用mv命令进行重命名。</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">4)函数</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">如果您写了一些稍微复杂一些的程序，您就会发现在程序中可能在几个地方使用了相同的代码，并且您也会发现，如果我们使用了函数，会方便很多。一个函数是这个样子的：</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />

<div class="code_main" style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left; color:rgb(102,102,102); padding-top:4px; padding-right:4px; padding-bottom:4px; padding-left:4px; margin-top:2px; margin-right:2px; margin-bottom:2px; margin-left:2px; border-top-width:1px; border-right-width:1px; border-bottom-width:1px; border-left-width:1px; border-top-style:dashed; border-right-style:dashed; border-bottom-style:dashed; border-left-style:dashed; border-top-color:rgb(102,102,102); border-right-color:rgb(102,102,102); border-bottom-color:rgb(102,102,102); border-left-color:rgb(102,102,102)">
	functionname()<br />
	{<br />
	# inside the body $1 is the first argument given to the function<br />
	# $2 the second ...<br />
	body<br />
	}
</div>
<br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">您需要在每个程序的开始对函数进行声明。</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">　　下面是一个叫做xtitlebar的脚本，使用这个脚本您可以改变终端窗口的名称。</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">这里使用了一个叫做help的函数。正如您可以看到的那样，这个定义的函数被使用了两次。</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />

<div class="code_main" style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left; color:rgb(102,102,102); padding-top:4px; padding-right:4px; padding-bottom:4px; padding-left:4px; margin-top:2px; margin-right:2px; margin-bottom:2px; margin-left:2px; border-top-width:1px; border-right-width:1px; border-bottom-width:1px; border-left-width:1px; border-top-style:dashed; border-right-style:dashed; border-bottom-style:dashed; border-left-style:dashed; border-top-color:rgb(102,102,102); border-right-color:rgb(102,102,102); border-bottom-color:rgb(102,102,102); border-left-color:rgb(102,102,102)">
	#!/bin/sh<br />
	# vim: set sw=4 ts=4 et:<br />
	help()<br />
	{<br />
	　　cat &lt;<br />
	xtitlebar -- change the name of an xterm, gnome-terminal or kde konsole<br />
	USAGE: xtitlebar [-h] &quot;string_for_titelbar&quot;<br />
	OPTIONS: -h help text<br />
	EXAMPLE: xtitlebar &quot;cvs&quot;<br />
	HELP<br />
	　　exit 0<br />
	}<br />
	# in case of error or if -h is given we call the function help:<br />
	[ -z &quot;$1&quot; ] &amp;&amp; help<br />
	[ &quot;$1&quot; = &quot;-h&quot; ] &amp;&amp; help<br />
	# send the escape sequence to change the xterm titelbar:<br />
	echo -e &quot;33]0;$107&quot;<br />
	#
</div>
<br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">在脚本中提供帮助是一种很好的编程习惯，这样方便其他用户（和您）使用和理解脚本。</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">命令行参数</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">　　我们已经见过$* 和 $1, $2 ... $9 等特殊变量，这些特殊变量包含了用户从命令行输入的参数。迄今为止，我们仅仅了解了一些简单的命令行语法（比如一些强制性的参数和查看帮助的-h选项）。但是在编写更复杂的程序时，您可能会发现您需要更多的自定义的选项。通常的惯例是在所有可选的参数之前加一个减号，后面再加上参数值 (比如文件名)。</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">有好多方法可以实现对输入参数的分析，但是下面的使用case表达式的例子无遗是一个不错的方法。</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />

<div class="code_main" style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left; color:rgb(102,102,102); padding-top:4px; padding-right:4px; padding-bottom:4px; padding-left:4px; margin-top:2px; margin-right:2px; margin-bottom:2px; margin-left:2px; border-top-width:1px; border-right-width:1px; border-bottom-width:1px; border-left-width:1px; border-top-style:dashed; border-right-style:dashed; border-bottom-style:dashed; border-left-style:dashed; border-top-color:rgb(102,102,102); border-right-color:rgb(102,102,102); border-bottom-color:rgb(102,102,102); border-left-color:rgb(102,102,102)">
	#!/bin/sh<br />
	help()<br />
	{<br />
	　cat &lt;<br />
	This is a generic command line parser demo.<br />
	USAGE EXAMPLE: cmdparser -l hello -f -- -somefile1 somefile2<br />
	HELP<br />
	　exit 0<br />
	}<br />
	while [ -n &quot;$1&quot; ]; do<br />
	case $1 in<br />
	　　-h) help;shift 1;; # function help is called<br />
	　　-f) opt_f=1;shift 1;; # variable opt_f is set<br />
	　　-l) opt_l=$2;shift 2;; # -l takes an argument -&gt; shift by 2<br />
	　　--) shift;break;; # end of options<br />
	　　-*) echo &quot;error: no such option $1. -h for help&quot;;exit 1;;<br />
	　　*) break;;<br />
	esac<br />
	done<br />
	echo &quot;opt_f is $opt_f&quot;<br />
	echo &quot;opt_l is $opt_l&quot;<br />
	echo &quot;first arg is $1&quot;<br />
	echo &quot;2nd arg is $2&quot;
</div>
<br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">　　您可以这样运行该脚本：</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />

<div class="code_main" style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left; color:rgb(102,102,102); padding-top:4px; padding-right:4px; padding-bottom:4px; padding-left:4px; margin-top:2px; margin-right:2px; margin-bottom:2px; margin-left:2px; border-top-width:1px; border-right-width:1px; border-bottom-width:1px; border-left-width:1px; border-top-style:dashed; border-right-style:dashed; border-bottom-style:dashed; border-left-style:dashed; border-top-color:rgb(102,102,102); border-right-color:rgb(102,102,102); border-bottom-color:rgb(102,102,102); border-left-color:rgb(102,102,102)">
	cmdparser -l hello -f -- -somefile1 somefile2
</div>
<br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">　　返回的结果是：</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />

<div class="code_main" style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left; color:rgb(102,102,102); padding-top:4px; padding-right:4px; padding-bottom:4px; padding-left:4px; margin-top:2px; margin-right:2px; margin-bottom:2px; margin-left:2px; border-top-width:1px; border-right-width:1px; border-bottom-width:1px; border-left-width:1px; border-top-style:dashed; border-right-style:dashed; border-bottom-style:dashed; border-left-style:dashed; border-top-color:rgb(102,102,102); border-right-color:rgb(102,102,102); border-bottom-color:rgb(102,102,102); border-left-color:rgb(102,102,102)">
	opt_f is 1<br />
	opt_l is hello<br />
	first arg is -somefile1<br />
	2nd arg is somefile2
</div>
<br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">　　这个脚本是如何工作的呢？脚本首先在所有输入命令行参数中进行循环，将输入参数与case表达式进行比较，如果匹配则设置一个变量并且移除该参数。根据unix系统的惯例，首先输入的应该是包含减号的参数.</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">第2部分 实例</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">现在我们来讨论编写一个脚本的一般步骤。任何优秀的脚本都应该具有帮助和输入参数。并且写一个伪脚本（framework.sh），该脚本包含了大多数脚本都需要的框架结构，是一个非常不错的主意。这时候，在写一个新的脚本时我们只需要执行一下copy命令：</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />

<div class="code_main" style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left; color:rgb(102,102,102); padding-top:4px; padding-right:4px; padding-bottom:4px; padding-left:4px; margin-top:2px; margin-right:2px; margin-bottom:2px; margin-left:2px; border-top-width:1px; border-right-width:1px; border-bottom-width:1px; border-left-width:1px; border-top-style:dashed; border-right-style:dashed; border-bottom-style:dashed; border-left-style:dashed; border-top-color:rgb(102,102,102); border-right-color:rgb(102,102,102); border-bottom-color:rgb(102,102,102); border-left-color:rgb(102,102,102)">
	cp framework.sh myscript
</div>
<br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">　然后再插入自己的函数。</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">　　让我们再看两个例子：</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">　　</span><span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">二进制到十进制的转换</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">　　脚本 b2d 将二进制数 (比如 1101) 转换为相应的十进制数。这也是一个用expr命令进行数学运算的例子：</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />

<div class="code_main" style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left; color:rgb(102,102,102); padding-top:4px; padding-right:4px; padding-bottom:4px; padding-left:4px; margin-top:2px; margin-right:2px; margin-bottom:2px; margin-left:2px; border-top-width:1px; border-right-width:1px; border-bottom-width:1px; border-left-width:1px; border-top-style:dashed; border-right-style:dashed; border-bottom-style:dashed; border-left-style:dashed; border-top-color:rgb(102,102,102); border-right-color:rgb(102,102,102); border-bottom-color:rgb(102,102,102); border-left-color:rgb(102,102,102)">
	#!/bin/sh<br />
	# vim: set sw=4 ts=4 et:<br />
	help()<br />
	{<br />
	　cat &lt;<br />
	b2h -- convert binary to decimal<br />
	USAGE: b2h [-h] binarynum<br />
	OPTIONS: -h help text<br />
	EXAMPLE: b2h 111010<br />
	will return 58<br />
	HELP<br />
	　exit 0<br />
	}<br />
	error()<br />
	{<br />
	　　# print an error and exit<br />
	　　echo &quot;$1&quot;<br />
	　　exit 1<br />
	}<br />
	lastchar()<br />
	{<br />
	　　# return the last character of a string in $rval<br />
	　　if [ -z &quot;$1&quot; ]; then<br />
	　　　　# empty string<br />
	　　　　rval=&quot;&quot;<br />
	　　　　return<br />
	　　fi<br />
	　　# wc puts some space behind the output this is why we need sed:<br />
	　　numofchar=`echo -n &quot;$1&quot; | wc -c | sed 's/ //g' `<br />
	　　# now cut out the last char<br />
	　　rval=`echo -n &quot;$1&quot; | cut -b $numofchar`<br />
	}<br />
	chop()<br />
	{<br />
	　　# remove the last character in string and return it in $rval<br />
	　　if [ -z &quot;$1&quot; ]; then<br />
	　　　　# empty string<br />
	　　　　rval=&quot;&quot;<br />
	　　　　return<br />
	　　fi<br />
	　　# wc puts some space behind the output this is why we need sed:<br />
	　　numofchar=`echo -n &quot;$1&quot; | wc -c | sed 's/ //g' `<br />
	　　if [ &quot;$numofchar&quot; = &quot;1&quot; ]; then<br />
	　　　　# only one char in string<br />
	　　　　rval=&quot;&quot;<br />
	　　　　return<br />
	　　fi<br />
	　　numofcharminus1=`expr $numofchar &quot;-&quot; 1`<br />
	　　# now cut all but the last char:<br />
	　　rval=`echo -n &quot;$1&quot; | cut -b 0-${numofcharminus1}`<br />
	}<br />
	while [ -n &quot;$1&quot; ]; do<br />
	case $1 in<br />
	　　-h) help;shift 1;; # function help is called<br />
	　　--) shift;break;; # end of options<br />
	　　-*) error &quot;error: no such option $1. -h for help&quot;;;<br />
	　　*) break;;<br />
	esac<br />
	done<br />
	# The main program<br />
	sum=0<br />
	weight=1<br />
	# one arg must be given:<br />
	[ -z &quot;$1&quot; ] &amp;&amp; help<br />
	binnum=&quot;$1&quot;<br />
	binnumorig=&quot;$1&quot;<br />
	while [ -n &quot;$binnum&quot; ]; do<br />
	　　lastchar &quot;$binnum&quot;<br />
	　　if [ &quot;$rval&quot; = &quot;1&quot; ]; then<br />
	　　　　sum=`expr &quot;$weight&quot; &quot;+&quot; &quot;$sum&quot;`<br />
	　　fi<br />
	　　# remove the last position in $binnum<br />
	　　chop &quot;$binnum&quot;<br />
	　　binnum=&quot;$rval&quot;<br />
	　　weight=`expr &quot;$weight&quot; &quot;*&quot; 2`<br />
	done<br />
	echo &quot;binary $binnumorig is decimal $sum&quot;
</div>
<br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">　该脚本使用的算法是利用十进制和二进制数权值 (1,2,4,8,16,..)，比如二进制&quot;10&quot;可以这样转换成十进制：</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">0 * 1 + 1 * 2 = 2</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">　　为了得到单个的二进制数我们是用了lastchar 函数。该函数使用wc –c计算字符个数，然后使用cut命令取出末尾一个字符。Chop函数的功能则是移除最后一个字符。</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">文件循环程序</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">　　或许您是想将所有发出的邮件保存到一个文件中的人们中的一员，但是在过了几个月以后，这个文件可能会变得很大以至于使对该文件的访问速度变慢。下面的脚本rotatefile可以解决这个问题。这个脚本可以重命名邮件保存文件（假设为outmail）为outmail.1，而对于outmail.1就变成了outmail.2 等等等等...</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />

<div class="code_main" style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left; color:rgb(102,102,102); padding-top:4px; padding-right:4px; padding-bottom:4px; padding-left:4px; margin-top:2px; margin-right:2px; margin-bottom:2px; margin-left:2px; border-top-width:1px; border-right-width:1px; border-bottom-width:1px; border-left-width:1px; border-top-style:dashed; border-right-style:dashed; border-bottom-style:dashed; border-left-style:dashed; border-top-color:rgb(102,102,102); border-right-color:rgb(102,102,102); border-bottom-color:rgb(102,102,102); border-left-color:rgb(102,102,102)">
	#!/bin/sh<br />
	# vim: set sw=4 ts=4 et:<br />
	ver=&quot;0.1&quot;<br />
	help()<br />
	{<br />
	　　cat &lt;<br />
	rotatefile -- rotate the file name<br />
	USAGE: rotatefile [-h] filename<br />
	OPTIONS: -h help text<br />
	EXAMPLE: rotatefile out<br />
	This will e.g rename out.2 to out.3, out.1 to out.2, out to out.1<br />
	and create an empty out-file<br />
	The max number is 10<br />
	version $ver<br />
	HELP<br />
	　　exit 0<br />
	}<br />
	error()<br />
	{<br />
	　　echo &quot;$1&quot;<br />
	　　exit 1<br />
	}<br />
	while [ -n &quot;$1&quot; ]; do<br />
	case $1 in<br />
	　　-h) help;shift 1;;<br />
	　　--) break;;<br />
	　　-*) echo &quot;error: no such option $1. -h for help&quot;;exit 1;;<br />
	　　*) break;;<br />
	esac<br />
	done<br />
	# input check:<br />
	if [ -z &quot;$1&quot; ] ; then<br />
	error &quot;ERROR: you must specify a file, use -h for help&quot;<br />
	fi<br />
	filen=&quot;$1&quot;<br />
	# rename any .1 , .2 etc file:<br />
	for n in 9 8 7 6 5 4 3 2 1; do<br />
	　　if [ -f &quot;$filen.$n&quot; ]; then<br />
	　　　　p=`expr $n + 1`<br />
	　　　　echo &quot;mv $filen.$n $filen.$p&quot;<br />
	　　　　mv $filen.$n $filen.$p<br />
	　　fi<br />
	done<br />
	# rename the original file:<br />
	if [ -f &quot;$filen&quot; ]; then<br />
	　　echo &quot;mv $filen $filen.1&quot;<br />
	　　mv $filen $filen.1<br />
	fi<br />
	echo touch $filen<br />
	touch $filen
</div>
<br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">　　这个脚本是如何工作的呢？在检测用户提供了一个文件名以后，我们进行一个9到1的循环。文件9被命名为10，文件8重命名为9等等。循环完成之后，我们将原始文件命名为文件1同时建立一个与原始文件同名的空文件。</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">调试</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">　　最简单的调试命令当然是使用</span><span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">echo命令</span><span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">。您可以使用echo在任何怀疑出错的地方打印任何变量值。这也是绝大多数的shell程序员要花费80%的时间来调试程序的原因。Shell程序的好处在于不需要重新编译，插入一个echo命令也不需要多少时间。</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">　　shell也有一个真实的调试模式。如果在脚本&quot;strangescript&quot; 中有错误，您可以这样来进行调试：</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />

<div class="code_main" style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left; color:rgb(102,102,102); padding-top:4px; padding-right:4px; padding-bottom:4px; padding-left:4px; margin-top:2px; margin-right:2px; margin-bottom:2px; margin-left:2px; border-top-width:1px; border-right-width:1px; border-bottom-width:1px; border-left-width:1px; border-top-style:dashed; border-right-style:dashed; border-bottom-style:dashed; border-left-style:dashed; border-top-color:rgb(102,102,102); border-right-color:rgb(102,102,102); border-bottom-color:rgb(102,102,102); border-left-color:rgb(102,102,102)">
	sh -x strangescript
</div>
<br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">　　这将执行该脚本并显示所有变量的值。</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">　　shell还有一个不需要执行脚本只是检查语法的模式。可以这样使用：</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />

<div class="code_main" style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left; color:rgb(102,102,102); padding-top:4px; padding-right:4px; padding-bottom:4px; padding-left:4px; margin-top:2px; margin-right:2px; margin-bottom:2px; margin-left:2px; border-top-width:1px; border-right-width:1px; border-bottom-width:1px; border-left-width:1px; border-top-style:dashed; border-right-style:dashed; border-bottom-style:dashed; border-left-style:dashed; border-top-color:rgb(102,102,102); border-right-color:rgb(102,102,102); border-bottom-color:rgb(102,102,102); border-left-color:rgb(102,102,102)">
	sh -n your_script
</div>
<br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">　　这将返回所有语法错误</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left"> </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">--------------------------------------------------------------------------------------------------</span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">shell编程简介</span><span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left"> </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">Bourne Shell</span><span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left"> </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">介绍：Bourne Shell 基础及其他很多有用的特性，shell编程及组织。 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">主要内容： </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">.shell基础 基本介绍，环境，选项，特殊字符 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">.shell变量 用户定义变量，环境变量，位置变量(shell 参数) </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">.shell script编程 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">条件测试，循环及重复控制 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">.shell定制 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">1.shell基础知识</span><span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left"> </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">作者：Stephen Bourne 在Bell实验室开发 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">建议：man sh 查看相关UNIX上的改进或特性 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">(1)shell提示符及其环境</span><span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left"> </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">/etc/passwd文件 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">提示符：$ </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />

<div class="code_main" style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left; color:rgb(102,102,102); padding-top:4px; padding-right:4px; padding-bottom:4px; padding-left:4px; margin-top:2px; margin-right:2px; margin-bottom:2px; margin-left:2px; border-top-width:1px; border-right-width:1px; border-bottom-width:1px; border-left-width:1px; border-top-style:dashed; border-right-style:dashed; border-bottom-style:dashed; border-left-style:dashed; border-top-color:rgb(102,102,102); border-right-color:rgb(102,102,102); border-bottom-color:rgb(102,102,102); border-left-color:rgb(102,102,102)">
	/etc/profile $HOME/.profile 
</div>
<br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">(2)shell执行选项</span><span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left"> </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">-n 测试shell script语法结构，只读取shell script但不执行 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">-x 进入跟踪方式，显示所执行的每一条命令，用于调度 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">-a Tag all variables for export </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">-c &quot;string&quot; 从strings中读取命令 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">-e 非交互方式 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">-f 关闭shell文件名产生功能 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">-h locate and remember functions as defind </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">-i 交互方式 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">-k 从环境变量中读取命令的参数 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">-r 限制方式 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">-s 从标准输入读取命令 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">-t 执行命令后退出(shell exits) </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">-u 在替换中如使用未定义变量为错误 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">-v verbose,显示shell输入行 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">这些选项可以联合使用，但有些显然相互冲突，如-e和-i. </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">(3)受限制shell(Restircted Shell) </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />

<div class="code_main" style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left; color:rgb(102,102,102); padding-top:4px; padding-right:4px; padding-bottom:4px; padding-left:4px; margin-top:2px; margin-right:2px; margin-bottom:2px; margin-left:2px; border-top-width:1px; border-right-width:1px; border-bottom-width:1px; border-left-width:1px; border-top-style:dashed; border-right-style:dashed; border-bottom-style:dashed; border-left-style:dashed; border-top-color:rgb(102,102,102); border-right-color:rgb(102,102,102); border-bottom-color:rgb(102,102,102); border-left-color:rgb(102,102,102)">
	sh -r 或 /bin/rsh
</div>
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left"> </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">不能执行如下操作：cd, 更改PATH,指定全路径名，输出重定向，因此可以提供一个较好的控制和安全机制。通常rsh用于应用型用户及拨号用户，这些用户通常是看不到提示符的。通常受限制用户的主目录是不可写的。 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">不足：如果用户可以调用sh,则rsh的限制将不在起作用，事实上如果用户在vi及more 程序中调用shell,而这时rsh的限制将不再起作用。 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">(4)用set改变 shell选项</span><span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left"> </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">用户可以在$提示符下用set命令来设置或取消shell的选项。使用-设置选项，+取消相应选项，大多数UNIX系统允许a,e,f,h,k,n,u,v和x的开关设置/取消。 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />

<div class="code_main" style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left; color:rgb(102,102,102); padding-top:4px; padding-right:4px; padding-bottom:4px; padding-left:4px; margin-top:2px; margin-right:2px; margin-bottom:2px; margin-left:2px; border-top-width:1px; border-right-width:1px; border-bottom-width:1px; border-left-width:1px; border-top-style:dashed; border-right-style:dashed; border-bottom-style:dashed; border-left-style:dashed; border-top-color:rgb(102,102,102); border-right-color:rgb(102,102,102); border-bottom-color:rgb(102,102,102); border-left-color:rgb(102,102,102)">
	set -xv
</div>
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left"> </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">启动跟踪方式;显示所有的命令及替换，同样显示输入。 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />

<div class="code_main" style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left; color:rgb(102,102,102); padding-top:4px; padding-right:4px; padding-bottom:4px; padding-left:4px; margin-top:2px; margin-right:2px; margin-bottom:2px; margin-left:2px; border-top-width:1px; border-right-width:1px; border-bottom-width:1px; border-left-width:1px; border-top-style:dashed; border-right-style:dashed; border-bottom-style:dashed; border-left-style:dashed; border-top-color:rgb(102,102,102); border-right-color:rgb(102,102,102); border-bottom-color:rgb(102,102,102); border-left-color:rgb(102,102,102)">
	set -tu
</div>
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left"> </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">关闭在替换时对未定义变量的检查。 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">使用echo $-显示所有已设置的shell选项。 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">(5)用户启动文件 .profile</span><span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left"> </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />

<div class="code_main" style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left; color:rgb(102,102,102); padding-top:4px; padding-right:4px; padding-bottom:4px; padding-left:4px; margin-top:2px; margin-right:2px; margin-bottom:2px; margin-left:2px; border-top-width:1px; border-right-width:1px; border-bottom-width:1px; border-left-width:1px; border-top-style:dashed; border-right-style:dashed; border-bottom-style:dashed; border-left-style:dashed; border-top-color:rgb(102,102,102); border-right-color:rgb(102,102,102); border-bottom-color:rgb(102,102,102); border-left-color:rgb(102,102,102)">
	PATH=$PATH:/usr/loacl/bin; export PATH 
</div>
<br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">(6)shell环境变量</span><span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left"> </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />

<div class="code_main" style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left; color:rgb(102,102,102); padding-top:4px; padding-right:4px; padding-bottom:4px; padding-left:4px; margin-top:2px; margin-right:2px; margin-bottom:2px; margin-left:2px; border-top-width:1px; border-right-width:1px; border-bottom-width:1px; border-left-width:1px; border-top-style:dashed; border-right-style:dashed; border-bottom-style:dashed; border-left-style:dashed; border-top-color:rgb(102,102,102); border-right-color:rgb(102,102,102); border-bottom-color:rgb(102,102,102); border-left-color:rgb(102,102,102)">
	CDPATH 用于cd命令的查找路径 <br />
	HOME /etc/passwd文件中列出的用户主目录 <br />
	IFS Internal Field Separator,默认为空格，tab及换行符 <br />
	MAIL /var/mail/$USERNAME mail等程序使用 <br />
	PATH <br />
	PS1，PS2 默认提示符($)及换行提示符(&gt;) <br />
	TERM 终端类型，常用的有vt100,ansi,vt200,xterm等
</div>
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left"> </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">示例：</span><span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left"></span>
<div class="code_main" style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left; color:rgb(102,102,102); padding-top:4px; padding-right:4px; padding-bottom:4px; padding-left:4px; margin-top:2px; margin-right:2px; margin-bottom:2px; margin-left:2px; border-top-width:1px; border-right-width:1px; border-bottom-width:1px; border-left-width:1px; border-top-style:dashed; border-right-style:dashed; border-bottom-style:dashed; border-left-style:dashed; border-top-color:rgb(102,102,102); border-right-color:rgb(102,102,102); border-bottom-color:rgb(102,102,102); border-left-color:rgb(102,102,102)">
	$PS1=&quot;test:&quot;;export PS1 <br />
	test: PS1=&quot;\$&quot;;export PS1 <br />
	$echo $MAIL <br />
	/var/mail/username 
</div>
<br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">(7)保留字符及其含义</span><span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left"> </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">$ shell变量名的开始，如$var </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">| 管道，将标准输出转到下一个命令的标准输入 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left"># 注释开始 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">&amp; 在后台执行一个进程 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">？ 匹配一个字符 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">* 匹配0到多个字符(与DOS不同，可在文件名中间使用，并且含.) </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">$- 使用set及执行时传递给shell的标志位 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">$! 最后一个子进程的进程号 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">$# 传递给shell script的参数个数 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">$* 传递给shell script的参数 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">$@ 所有参数，个别的用双引号括起来 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">$? 上一个命令的返回代码 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">$0 当前shell的名字 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">$n (n:1-) 位置参数 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">$$ 进程标识号(Process Identifier Number, PID) </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">&gt;file 输出重定向 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">`command` 命令替换，如 filename=`basename /usr/local/bin/tcsh` </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">&gt;&gt;fiile 输出重定向，append </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">转义符及单引号： </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />

<div class="code_main" style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left; color:rgb(102,102,102); padding-top:4px; padding-right:4px; padding-bottom:4px; padding-left:4px; margin-top:2px; margin-right:2px; margin-bottom:2px; margin-left:2px; border-top-width:1px; border-right-width:1px; border-bottom-width:1px; border-left-width:1px; border-top-style:dashed; border-right-style:dashed; border-bottom-style:dashed; border-left-style:dashed; border-top-color:rgb(102,102,102); border-right-color:rgb(102,102,102); border-bottom-color:rgb(102,102,102); border-left-color:rgb(102,102,102)">
	$echo &quot;$HOME $PATH&quot; <br />
	/home/hbwork /opt/kde/bin:/usr/local/bin:/bin:/usr/bin:/usr/X11R6/bin: <br />
	$echo '$HOME $PATH' <br />
	$HOME $PATH <br />
	$echo \$HOME $PATH <br />
	$HOME /opt/kde/bin:/usr/local/bin:/bin:/usr/bin:/usr/X11R6/bin:/home/hbwork/bin 
</div>
<br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">其他： </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />

<div class="code_main" style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left; color:rgb(102,102,102); padding-top:4px; padding-right:4px; padding-bottom:4px; padding-left:4px; margin-top:2px; margin-right:2px; margin-bottom:2px; margin-left:2px; border-top-width:1px; border-right-width:1px; border-bottom-width:1px; border-left-width:1px; border-top-style:dashed; border-right-style:dashed; border-bottom-style:dashed; border-left-style:dashed; border-top-color:rgb(102,102,102); border-right-color:rgb(102,102,102); border-bottom-color:rgb(102,102,102); border-left-color:rgb(102,102,102)">
	$dir=ls <br />
	$$dir <br />
	$alias dir ls <br />
	$dir <br />
	ls &gt; filelist <br />
	ls &gt;&gt; filelist <br />
	wc -l &lt; filelist <br />
	wc -l filelist <br />
	sleep 5; echo 5 seconds reaches; ls -l <br />
	ps ax |egrep inetd <br />
	find / -name core -exec rm {} \; &amp; <br />
	filename=`date &quot;+%Y%m%d&quot;`.log 
</div>
<br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">2. shell变量</span><span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left"> </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">变量：代表某些值的符号，如$HOME,cd命令查找$HOME,在计算机语言中可以使用变量可以进行多种运算和控制。 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">Bourne Shell有如下四种变量： </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">.用户自定义变量 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">.位置变量即 shell script之参数 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">.预定义变量（特殊变量） </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">.环境变量(参考shell定制部分) </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">(1)用户自定义变量（数据的存储）</span><span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left"> </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />

<div class="code_main" style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left; color:rgb(102,102,102); padding-top:4px; padding-right:4px; padding-bottom:4px; padding-left:4px; margin-top:2px; margin-right:2px; margin-bottom:2px; margin-left:2px; border-top-width:1px; border-right-width:1px; border-bottom-width:1px; border-left-width:1px; border-top-style:dashed; border-right-style:dashed; border-bottom-style:dashed; border-left-style:dashed; border-top-color:rgb(102,102,102); border-right-color:rgb(102,102,102); border-bottom-color:rgb(102,102,102); border-left-color:rgb(102,102,102)">
	$ COUNT=1 <br />
	$ NAME=&quot;He Binwu&quot; 
</div>
<br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">技巧：因为大部分UNIX命令使用小写字符，因此在shell编程中通常使用全大写变量，当然这并不是强制性的，但使用大写字符可以在编程中方便地识别变量。 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">变量的调用：在变量前加$ </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />

<div class="code_main" style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left; color:rgb(102,102,102); padding-top:4px; padding-right:4px; padding-bottom:4px; padding-left:4px; margin-top:2px; margin-right:2px; margin-bottom:2px; margin-left:2px; border-top-width:1px; border-right-width:1px; border-bottom-width:1px; border-left-width:1px; border-top-style:dashed; border-right-style:dashed; border-bottom-style:dashed; border-left-style:dashed; border-top-color:rgb(102,102,102); border-right-color:rgb(102,102,102); border-bottom-color:rgb(102,102,102); border-left-color:rgb(102,102,102)">
	$ echo $HOME <br />
	/home/hbwork <br />
	$ WEEK=Satur <br />
	$ echo Today is $WEEKday <br />
	Today is <br />
	$echo Today is ${WEEK}day <br />
	Today is Saturday 
</div>
<br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">Shell变量赋值从右从左进行(Linux Shell/bash从左向右赋值!) </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />

<div class="code_main" style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left; color:rgb(102,102,102); padding-top:4px; padding-right:4px; padding-bottom:4px; padding-left:4px; margin-top:2px; margin-right:2px; margin-bottom:2px; margin-left:2px; border-top-width:1px; border-right-width:1px; border-bottom-width:1px; border-left-width:1px; border-top-style:dashed; border-right-style:dashed; border-bottom-style:dashed; border-left-style:dashed; border-top-color:rgb(102,102,102); border-right-color:rgb(102,102,102); border-bottom-color:rgb(102,102,102); border-left-color:rgb(102,102,102)">
	$ X=$Y Y=y <br />
	$ echo $X <br />
	y <br />
	$ Z=z Y=$Z <br />
	$ echo $Y <br />
	$ 
</div>
<br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">使用unset命令删除变量的赋值 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />

<div class="code_main" style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left; color:rgb(102,102,102); padding-top:4px; padding-right:4px; padding-bottom:4px; padding-left:4px; margin-top:2px; margin-right:2px; margin-bottom:2px; margin-left:2px; border-top-width:1px; border-right-width:1px; border-bottom-width:1px; border-left-width:1px; border-top-style:dashed; border-right-style:dashed; border-bottom-style:dashed; border-left-style:dashed; border-top-color:rgb(102,102,102); border-right-color:rgb(102,102,102); border-bottom-color:rgb(102,102,102); border-left-color:rgb(102,102,102)">
	$ Z=hello <br />
	$ echo $Z <br />
	hello <br />
	$ unset Z <br />
	$ echo $Z <br />
	$ 
</div>
<br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">有条件的命令替换</span><span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left"> </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">在Bourne Shell中可以使变量替换在特定条件下执行，即有条件的环境变量替换。 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">这种变量替换总是用大括号括起来的。 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">.设置变量的默认值 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">在变量未赋值之前其值为空。Bourne Shell允许对变量设置默认值，其格式如下： </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />

<div class="code_main" style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left; color:rgb(102,102,102); padding-top:4px; padding-right:4px; padding-bottom:4px; padding-left:4px; margin-top:2px; margin-right:2px; margin-bottom:2px; margin-left:2px; border-top-width:1px; border-right-width:1px; border-bottom-width:1px; border-left-width:1px; border-top-style:dashed; border-right-style:dashed; border-bottom-style:dashed; border-left-style:dashed; border-top-color:rgb(102,102,102); border-right-color:rgb(102,102,102); border-bottom-color:rgb(102,102,102); border-left-color:rgb(102,102,102)">
	${variable:-defaultvalue} 
</div>
<br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">例： </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />

<div class="code_main" style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left; color:rgb(102,102,102); padding-top:4px; padding-right:4px; padding-bottom:4px; padding-left:4px; margin-top:2px; margin-right:2px; margin-bottom:2px; margin-left:2px; border-top-width:1px; border-right-width:1px; border-bottom-width:1px; border-left-width:1px; border-top-style:dashed; border-right-style:dashed; border-bottom-style:dashed; border-left-style:dashed; border-top-color:rgb(102,102,102); border-right-color:rgb(102,102,102); border-bottom-color:rgb(102,102,102); border-left-color:rgb(102,102,102)">
	$ echo Hello $UNAME <br />
	Hello <br />
	$ echo Hello ${UNAME:-there} <br />
	Hello there <br />
	$ echo $UNAME #变量值并未发生变化 <br />
	$ UNAME=hbwork <br />
	$ echo Hello ${UNAME:-there} <br />
	Hello hbwork <br />
	$ 
</div>
<br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">.另一种情况：改变变量的值，格式如下： </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />

<div class="code_main" style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left; color:rgb(102,102,102); padding-top:4px; padding-right:4px; padding-bottom:4px; padding-left:4px; margin-top:2px; margin-right:2px; margin-bottom:2px; margin-left:2px; border-top-width:1px; border-right-width:1px; border-bottom-width:1px; border-left-width:1px; border-top-style:dashed; border-right-style:dashed; border-bottom-style:dashed; border-left-style:dashed; border-top-color:rgb(102,102,102); border-right-color:rgb(102,102,102); border-bottom-color:rgb(102,102,102); border-left-color:rgb(102,102,102)">
	${variable:=value}
</div>
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left"> </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">例： </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />

<div class="code_main" style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left; color:rgb(102,102,102); padding-top:4px; padding-right:4px; padding-bottom:4px; padding-left:4px; margin-top:2px; margin-right:2px; margin-bottom:2px; margin-left:2px; border-top-width:1px; border-right-width:1px; border-bottom-width:1px; border-left-width:1px; border-top-style:dashed; border-right-style:dashed; border-bottom-style:dashed; border-left-style:dashed; border-top-color:rgb(102,102,102); border-right-color:rgb(102,102,102); border-bottom-color:rgb(102,102,102); border-left-color:rgb(102,102,102)">
	$ echo Hello $UNAME <br />
	Hello <br />
	$ echo Hello ${UNAME:=there} <br />
	Hello there <br />
	$ echo $UNAME #变量值并未发生变化 <br />
	there <br />
	$
</div>
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left"> </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">.变量替换中使用命令替换 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />

<div class="code_main" style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left; color:rgb(102,102,102); padding-top:4px; padding-right:4px; padding-bottom:4px; padding-left:4px; margin-top:2px; margin-right:2px; margin-bottom:2px; margin-left:2px; border-top-width:1px; border-right-width:1px; border-bottom-width:1px; border-left-width:1px; border-top-style:dashed; border-right-style:dashed; border-bottom-style:dashed; border-left-style:dashed; border-top-color:rgb(102,102,102); border-right-color:rgb(102,102,102); border-bottom-color:rgb(102,102,102); border-left-color:rgb(102,102,102)">
	$USERDIR=${$MYDIR:-`pwd`} 
</div>
<br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">.在变量已赋值时进行替换 </span><span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left"></span>
<div class="code_main" style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left; color:rgb(102,102,102); padding-top:4px; padding-right:4px; padding-bottom:4px; padding-left:4px; margin-top:2px; margin-right:2px; margin-bottom:2px; margin-left:2px; border-top-width:1px; border-right-width:1px; border-bottom-width:1px; border-left-width:1px; border-top-style:dashed; border-right-style:dashed; border-bottom-style:dashed; border-left-style:dashed; border-top-color:rgb(102,102,102); border-right-color:rgb(102,102,102); border-bottom-color:rgb(102,102,102); border-left-color:rgb(102,102,102)">
	${variable:+value}
</div>
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left"> </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">.带有错误检查的有条件变量替换 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />

<div class="code_main" style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left; color:rgb(102,102,102); padding-top:4px; padding-right:4px; padding-bottom:4px; padding-left:4px; margin-top:2px; margin-right:2px; margin-bottom:2px; margin-left:2px; border-top-width:1px; border-right-width:1px; border-bottom-width:1px; border-left-width:1px; border-top-style:dashed; border-right-style:dashed; border-bottom-style:dashed; border-left-style:dashed; border-top-color:rgb(102,102,102); border-right-color:rgb(102,102,102); border-bottom-color:rgb(102,102,102); border-left-color:rgb(102,102,102)">
	${variable:?value}
</div>
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left"> </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">例： </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />

<div class="code_main" style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left; color:rgb(102,102,102); padding-top:4px; padding-right:4px; padding-bottom:4px; padding-left:4px; margin-top:2px; margin-right:2px; margin-bottom:2px; margin-left:2px; border-top-width:1px; border-right-width:1px; border-bottom-width:1px; border-left-width:1px; border-top-style:dashed; border-right-style:dashed; border-bottom-style:dashed; border-left-style:dashed; border-top-color:rgb(102,102,102); border-right-color:rgb(102,102,102); border-bottom-color:rgb(102,102,102); border-left-color:rgb(102,102,102)">
	$ UNAME= <br />
	$ echo ${UNAME:?&quot;UNAME has not been set&quot;} <br />
	UNAME: UNAME has not been set <br />
	$ echo ${UNAME:?} <br />
	UNAME: parameter null or not set 
</div>
<br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">(2)位置变量(Shell参数) </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">在shell script中位置参数可用$1..$9表示，$0表示内容通常为当前执行程序的文件名。 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">.防止变量值被替换 readonly variable </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">.使用export命令输出变量，使得变量对子shell可用，当shell执行一下程序时，shell将为其设置一个新的环境让其执行，这称之了subshell. 在Bourne Shell中变量通常被认为是本地变量，也就是说在对其赋值之外的shell环境之外是不认识此变量的。使用export对subshell可用。 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">例：对变量PS1的export操作，shell的提示符将发生变化。 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />

<div class="code_main" style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left; color:rgb(102,102,102); padding-top:4px; padding-right:4px; padding-bottom:4px; padding-left:4px; margin-top:2px; margin-right:2px; margin-bottom:2px; margin-left:2px; border-top-width:1px; border-right-width:1px; border-bottom-width:1px; border-left-width:1px; border-top-style:dashed; border-right-style:dashed; border-bottom-style:dashed; border-left-style:dashed; border-top-color:rgb(102,102,102); border-right-color:rgb(102,102,102); border-bottom-color:rgb(102,102,102); border-left-color:rgb(102,102,102)">
	$ PS1=`hostname`$ <br />
	peony$sh <br />
	$ echo $PS1 <br />
	$ &lt;-输出结果 <br />
	$ exit <br />
	peony$export PS1 <br />
	peony$sh <br />
	peony$ echo $PS1 <br />
	peony$ &lt;-输出结果 <br />
	peony$
</div>
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left"> </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">3.Shell Script编程</span><span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left"> </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">目的：使用UNIX所提供的最常用工具来完成所需复杂任务的强大功能。 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">(1)最简单的Shell 编程</span><span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left"> </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />

<div class="code_main" style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left; color:rgb(102,102,102); padding-top:4px; padding-right:4px; padding-bottom:4px; padding-left:4px; margin-top:2px; margin-right:2px; margin-bottom:2px; margin-left:2px; border-top-width:1px; border-right-width:1px; border-bottom-width:1px; border-left-width:1px; border-top-style:dashed; border-right-style:dashed; border-bottom-style:dashed; border-left-style:dashed; border-top-color:rgb(102,102,102); border-right-color:rgb(102,102,102); border-bottom-color:rgb(102,102,102); border-left-color:rgb(102,102,102)">
	$ls -R / |grep myname |more
</div>
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left"> </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">每天数据的备份： </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />

<div class="code_main" style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left; color:rgb(102,102,102); padding-top:4px; padding-right:4px; padding-bottom:4px; padding-left:4px; margin-top:2px; margin-right:2px; margin-bottom:2px; margin-left:2px; border-top-width:1px; border-right-width:1px; border-bottom-width:1px; border-left-width:1px; border-top-style:dashed; border-right-style:dashed; border-bottom-style:dashed; border-left-style:dashed; border-top-color:rgb(102,102,102); border-right-color:rgb(102,102,102); border-bottom-color:rgb(102,102,102); border-left-color:rgb(102,102,102)">
	$ cd /usr/yourname; ls * |cpio -o &gt; /dev/rmt/0h 
</div>
<br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">书写程序的目的是一次编程，多次使用（执行）！ </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />

<div class="code_main" style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left; color:rgb(102,102,102); padding-top:4px; padding-right:4px; padding-bottom:4px; padding-left:4px; margin-top:2px; margin-right:2px; margin-bottom:2px; margin-left:2px; border-top-width:1px; border-right-width:1px; border-bottom-width:1px; border-left-width:1px; border-top-style:dashed; border-right-style:dashed; border-bottom-style:dashed; border-left-style:dashed; border-top-color:rgb(102,102,102); border-right-color:rgb(102,102,102); border-bottom-color:rgb(102,102,102); border-left-color:rgb(102,102,102)">
	$ cat &gt; backup.sh <br />
	cd /home/hbwork <br />
	ls * | cpio -o &gt; /dev/rmt/0h <br />
	^D
</div>
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left"> </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">执行： </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />

<div class="code_main" style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left; color:rgb(102,102,102); padding-top:4px; padding-right:4px; padding-bottom:4px; padding-left:4px; margin-top:2px; margin-right:2px; margin-bottom:2px; margin-left:2px; border-top-width:1px; border-right-width:1px; border-bottom-width:1px; border-left-width:1px; border-top-style:dashed; border-right-style:dashed; border-bottom-style:dashed; border-left-style:dashed; border-top-color:rgb(102,102,102); border-right-color:rgb(102,102,102); border-bottom-color:rgb(102,102,102); border-left-color:rgb(102,102,102)">
	$ sh backup.sh 
</div>
<br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">或： </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />

<div class="code_main" style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left; color:rgb(102,102,102); padding-top:4px; padding-right:4px; padding-bottom:4px; padding-left:4px; margin-top:2px; margin-right:2px; margin-bottom:2px; margin-left:2px; border-top-width:1px; border-right-width:1px; border-bottom-width:1px; border-left-width:1px; border-top-style:dashed; border-right-style:dashed; border-bottom-style:dashed; border-left-style:dashed; border-top-color:rgb(102,102,102); border-right-color:rgb(102,102,102); border-bottom-color:rgb(102,102,102); border-left-color:rgb(102,102,102)">
	$ chmod +x backup.sh <br />
	$ ./backup.sh 
</div>
<br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">技巧：在shell script中加入必要的注释，以便以后阅读及维护。 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">(2)shell是一个（编程）语言</span><span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left"> </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">同传统的编程语言一样，shell提供了很多特性，这些特性可以使你的shell script 编程更为有用，如：数据变量、参数传递、判断、流程控制、数据输入和输出，子程序及以中断处理等。 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">. 在shell编程中使用数据变量可以将程序变量更为通用，如在上面backup.sh中： </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />

<div class="code_main" style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left; color:rgb(102,102,102); padding-top:4px; padding-right:4px; padding-bottom:4px; padding-left:4px; margin-top:2px; margin-right:2px; margin-bottom:2px; margin-left:2px; border-top-width:1px; border-right-width:1px; border-bottom-width:1px; border-left-width:1px; border-top-style:dashed; border-right-style:dashed; border-bottom-style:dashed; border-left-style:dashed; border-top-color:rgb(102,102,102); border-right-color:rgb(102,102,102); border-bottom-color:rgb(102,102,102); border-left-color:rgb(102,102,102)">
	cd $WORKDIR <br />
	ls * | cpio -o &gt; /dev/rmt/0h 
</div>
<br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">. Shell编程中的注释以#开头 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">. 对shell变量进行数字运算，使用expr命令 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />

<div class="code_main" style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left; color:rgb(102,102,102); padding-top:4px; padding-right:4px; padding-bottom:4px; padding-left:4px; margin-top:2px; margin-right:2px; margin-bottom:2px; margin-left:2px; border-top-width:1px; border-right-width:1px; border-bottom-width:1px; border-left-width:1px; border-top-style:dashed; border-right-style:dashed; border-bottom-style:dashed; border-left-style:dashed; border-top-color:rgb(102,102,102); border-right-color:rgb(102,102,102); border-bottom-color:rgb(102,102,102); border-left-color:rgb(102,102,102)">
	expr integer operator integer 
</div>
<br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">其中operator为+ - * / %, 但对*的使用要用转义符\,如： </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />

<div class="code_main" style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left; color:rgb(102,102,102); padding-top:4px; padding-right:4px; padding-bottom:4px; padding-left:4px; margin-top:2px; margin-right:2px; margin-bottom:2px; margin-left:2px; border-top-width:1px; border-right-width:1px; border-bottom-width:1px; border-left-width:1px; border-top-style:dashed; border-right-style:dashed; border-bottom-style:dashed; border-left-style:dashed; border-top-color:rgb(102,102,102); border-right-color:rgb(102,102,102); border-bottom-color:rgb(102,102,102); border-left-color:rgb(102,102,102)">
	$expr 4 \* 5 <br />
	20 <br />
	$int=`expr 5 + 7` <br />
	$echo $int <br />
	12 
</div>
<br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">(3)Shell编程的参数传递, 可通过命令行参数以及交互式输入变量(read)</span><span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left"> </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">restoreall.sh 对backup.sh程序的备份磁带进行恢复 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />

<div class="code_main" style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left; color:rgb(102,102,102); padding-top:4px; padding-right:4px; padding-bottom:4px; padding-left:4px; margin-top:2px; margin-right:2px; margin-bottom:2px; margin-left:2px; border-top-width:1px; border-right-width:1px; border-bottom-width:1px; border-left-width:1px; border-top-style:dashed; border-right-style:dashed; border-bottom-style:dashed; border-left-style:dashed; border-top-color:rgb(102,102,102); border-right-color:rgb(102,102,102); border-bottom-color:rgb(102,102,102); border-left-color:rgb(102,102,102)">
	$cat &gt; restoreall.sh <br />
	cd $WORKDIR <br />
	cpio -i &lt; /dev/rmt/0h <br />
	^D 
</div>
<br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">restore1.sh:只能恢复一个文件 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />

<div class="code_main" style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left; color:rgb(102,102,102); padding-top:4px; padding-right:4px; padding-bottom:4px; padding-left:4px; margin-top:2px; margin-right:2px; margin-bottom:2px; margin-left:2px; border-top-width:1px; border-right-width:1px; border-bottom-width:1px; border-left-width:1px; border-top-style:dashed; border-right-style:dashed; border-bottom-style:dashed; border-left-style:dashed; border-top-color:rgb(102,102,102); border-right-color:rgb(102,102,102); border-bottom-color:rgb(102,102,102); border-left-color:rgb(102,102,102)">
	#restore1 --program to restore a single file <br />
	cd $WORKDIR <br />
	cpio -i $i &lt; /dev/rmt/0h <br />
	$restore1 file1 
</div>
<br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">恢复多个文件restoreany : </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />

<div class="code_main" style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left; color:rgb(102,102,102); padding-top:4px; padding-right:4px; padding-bottom:4px; padding-left:4px; margin-top:2px; margin-right:2px; margin-bottom:2px; margin-left:2px; border-top-width:1px; border-right-width:1px; border-bottom-width:1px; border-left-width:1px; border-top-style:dashed; border-right-style:dashed; border-bottom-style:dashed; border-left-style:dashed; border-top-color:rgb(102,102,102); border-right-color:rgb(102,102,102); border-bottom-color:rgb(102,102,102); border-left-color:rgb(102,102,102)">
	#restoreany --program to restore a single file <br />
	cd $WORKDIR <br />
	cpio -i $* &lt; /dev/rmt/0h <br />
	$ restoreany file1 file2 file3 
</div>
<br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">(4)条件判断</span><span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left"> </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">. if-then语句,格式如下: </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />

<div class="code_main" style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left; color:rgb(102,102,102); padding-top:4px; padding-right:4px; padding-bottom:4px; padding-left:4px; margin-top:2px; margin-right:2px; margin-bottom:2px; margin-left:2px; border-top-width:1px; border-right-width:1px; border-bottom-width:1px; border-left-width:1px; border-top-style:dashed; border-right-style:dashed; border-bottom-style:dashed; border-left-style:dashed; border-top-color:rgb(102,102,102); border-right-color:rgb(102,102,102); border-bottom-color:rgb(102,102,102); border-left-color:rgb(102,102,102)">
	if command_1 <br />
	then <br />
	command_2 <br />
	command_3 <br />
	fi <br />
	command_4
</div>
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left"> </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">在if-then语句中使用了命令返回码$?,即当command_1执行成功时才执行command_2和 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">command_3,而command_4总是执行. </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">示例程序unload: 在备份成功时删除原始文件,带有错误检查 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />

<div class="code_main" style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left; color:rgb(102,102,102); padding-top:4px; padding-right:4px; padding-bottom:4px; padding-left:4px; margin-top:2px; margin-right:2px; margin-bottom:2px; margin-left:2px; border-top-width:1px; border-right-width:1px; border-bottom-width:1px; border-left-width:1px; border-top-style:dashed; border-right-style:dashed; border-bottom-style:dashed; border-left-style:dashed; border-top-color:rgb(102,102,102); border-right-color:rgb(102,102,102); border-bottom-color:rgb(102,102,102); border-left-color:rgb(102,102,102)">
	cd $1 <br />
	#备份时未考虑不成功的情况! <br />
	ls -a | cpio -o &gt; /dev/rmt/0h <br />
	rm -rf *
</div>
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left"> </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">改进如下: </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />

<div class="code_main" style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left; color:rgb(102,102,102); padding-top:4px; padding-right:4px; padding-bottom:4px; padding-left:4px; margin-top:2px; margin-right:2px; margin-bottom:2px; margin-left:2px; border-top-width:1px; border-right-width:1px; border-bottom-width:1px; border-left-width:1px; border-top-style:dashed; border-right-style:dashed; border-bottom-style:dashed; border-left-style:dashed; border-top-color:rgb(102,102,102); border-right-color:rgb(102,102,102); border-bottom-color:rgb(102,102,102); border-left-color:rgb(102,102,102)">
	#当使用了管道命令时,管理命令的返回代码为最后一个命令的返回代码 <br />
	if ls -a | cpio -o &gt; /dev/rmt/0h <br />
	then <br />
	rm -rf * <br />
	fi
</div>
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left"> </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">. if-then-else语句 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />

<div class="code_main" style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left; color:rgb(102,102,102); padding-top:4px; padding-right:4px; padding-bottom:4px; padding-left:4px; margin-top:2px; margin-right:2px; margin-bottom:2px; margin-left:2px; border-top-width:1px; border-right-width:1px; border-bottom-width:1px; border-left-width:1px; border-top-style:dashed; border-right-style:dashed; border-bottom-style:dashed; border-left-style:dashed; border-top-color:rgb(102,102,102); border-right-color:rgb(102,102,102); border-bottom-color:rgb(102,102,102); border-left-color:rgb(102,102,102)">
	if command_1 <br />
	then <br />
	command_2 <br />
	else <br />
	command_3 <br />
	fi 
</div>
<br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">技巧: 由于shell对命令中的多余的空格不作任何处理,一个好的程序员会用这一特性对自己的程序采用统一的缩进格式,以增强自己程序的可读性. </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">. 使用test命令进行进行条件测试 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">格式: test conditions </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">test在以下四种情况下使用: a. 字符比较 b.两个整数值的比较 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">c. 文件操作,如文件是否存在及文件的状态等 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">d. 逻辑操作,可以进行and/or,与其他条件联合使用 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">a. 测试字符数据: shell变量通常民政部下均作为字符变量 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">str1 = str2 二者相长,相同 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">str1 != str2 不同 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">-n string string不为空(长度不为零) </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">-z string string为空 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">string string不为空 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">例: </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />

<div class="code_main" style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left; color:rgb(102,102,102); padding-top:4px; padding-right:4px; padding-bottom:4px; padding-left:4px; margin-top:2px; margin-right:2px; margin-bottom:2px; margin-left:2px; border-top-width:1px; border-right-width:1px; border-bottom-width:1px; border-left-width:1px; border-top-style:dashed; border-right-style:dashed; border-bottom-style:dashed; border-left-style:dashed; border-top-color:rgb(102,102,102); border-right-color:rgb(102,102,102); border-bottom-color:rgb(102,102,102); border-left-color:rgb(102,102,102)">
	$ str1=abcd #在含有空格时必须用引号括起来 <br />
	$ test $str1=abcd <br />
	$ echo $? <br />
	0 <br />
	$ str1=&quot;abcd &quot; <br />
	$ test $str1=abcd <br />
	$ echo $? <br />
	1 
</div>
<br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">Note: 在test处理含有空格的变量时最好用引号将变量括起来,否则会出现错误的结果, </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">因为shell在处理命令行时将会去掉多余的空格,而用引号括起来则可以防止 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">shell去掉这些空格. </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">例: </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />

<div class="code_main" style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left; color:rgb(102,102,102); padding-top:4px; padding-right:4px; padding-bottom:4px; padding-left:4px; margin-top:2px; margin-right:2px; margin-bottom:2px; margin-left:2px; border-top-width:1px; border-right-width:1px; border-bottom-width:1px; border-left-width:1px; border-top-style:dashed; border-right-style:dashed; border-bottom-style:dashed; border-left-style:dashed; border-top-color:rgb(102,102,102); border-right-color:rgb(102,102,102); border-bottom-color:rgb(102,102,102); border-left-color:rgb(102,102,102)">
	$ str1=&quot; &quot; <br />
	$ test $str1 <br />
	$ echo $? <br />
	1 <br />
	$ test &quot;$str1&quot; <br />
	$ echo $? <br />
	0 <br />
	$ test -n $str1 <br />
	test: argument expected <br />
	$ test -n &quot;$str1&quot; <br />
	$ echo $? <br />
	0 <br />
	$
</div>
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left"> </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">b. 整数测试: test与expr相同,可以将字符型变量转换为整数进行操作,expr进行 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">整数的算术运算,而test则进行逻辑运算. </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">表达式 说明 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">--------------------------------------- </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">int1 -eq int2 相等? </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">int1 -ne int2 不等? </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">int1 -gt int2 int1 &gt; int2 ? </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">int1 -ge int2 int1 &gt;= int2 ? </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">int1 -lt int2 int1 &lt; int2 ? </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">int1 -le int2 int1 &lt;= int2 ? </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">例: </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">$ int1=1234 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">$ int2=01234 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">$ test $int1 -eq $int2 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">$ echo $? </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">0 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">c. 文件测试:检查文件状态如存在及读写权限等 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">-r filename 用户对文件filename有读权限? </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">-w filename 用户对文件filename有写权限? </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">-x filename 用户对文件filename有可执行权限? </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">-f filename 文件filename为普通文件? </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">-d filename 文件filename为目录? </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">-c filename 文件filename为字符设备文件? </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">-b filename 文件filename为块设备文件? </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">-s filename 文件filename大小不为零? </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">-t fnumb 与文件描述符fnumb(默认值为1)相关的设备是一个终端设备? </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">d. 测试条件之否定,使用! </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">例: </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">$ cat /dev/null &gt; empty </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">$ test -r empty </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">$ echo $? </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">0 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">$ test -s empty </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">1 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">$ test ! -s empty </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">$ echo $? </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">0 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">e. 测试条件之逻辑运算 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">-a And </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">-o Or </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">例: $ test -r empty -a -s empty </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">$ echo $? </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">1 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">f. 进行test测试的标准方法 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">因为test命令在 shell编程中占有很重要的地位,为了使shell能同其他编程语言一样 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">便于阅读和组织, Bourne Shell在使用test测试时使用了另一种方法:用方括号将整个 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">test测试括起来: </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">$ int1=4 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">$ [ $int1 -gt 2 ] </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">$ echo $? </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">0 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">例: 重写unload程序,使用test测试 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">#!/bin/sh </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">#unload - program to backup and remove files </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">#syntax: unload directory </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">#check arguments </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">if [ $# -ne 1 ] </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">then </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">echo &quot;usage: $0 directory&quot; </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">exit 1 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">fi </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">#check for valid directory name </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">if [ ! -d &quot;$1&quot; ] </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">then </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">echo &quot;$1 is not a directory&quot; </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">exit 2 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">fi </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">cd $1 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">ls -a | cpio -o &gt; /dev/rmt/0h </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">if [ $? -eq 0 ] </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">then </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">rm -rf * </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">else </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">echo &quot;A problem has occured in creating backup&quot; </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">echo &quot;The directory will not be ereased&quot; </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">echo &quot;Please check the backup device&quot; </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">exit 3 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">fi </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left"># end of unload </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">在如上示例中出现了exit, exit有两个作用:一是停止程序中其他命令的执行,二是 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">设置程序的退出状态 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">g. if嵌套及elif结构 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">if command </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">then </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">command </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">else </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">if command </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">then </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">command </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">else </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">if command </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">then </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">command </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">fi </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">fi </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">fi </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">改进:使用elif结构 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">if command </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">then </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">command </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">elif command </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">then </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">command </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">elif command </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">then </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">command </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">fi </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">elif结构同if结构类似,但结构更清淅,其执行结果完全相同. </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">h.交互式从键盘读入数据 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">使用read语句，其格式如下： </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">read var1 var2 ... varn </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">read将不作变量替换，但会删除多余的空格，直到遇到第一个换行符（回车）， </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">并将输入值依次赋值给相应的变量。 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">例： </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">$ read var1 var2 var3 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">Hello my friends </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">$ echo $var1 $var2 $var3 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">Hello my friends </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">$ echo $var1 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">Hello </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">$ read var1 var2 var3 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">Hello my dear friends </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">$ echo $var3 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">dear friends &lt;-输入多余变量时，输入值余下的内容赋给最后一个变量 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">$ read var1 var2 var3 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">Hello friends </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">$ echo $var3 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">&lt;- var3为空 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">$ </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">在shell script中可使用read语句进行交互操作： </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">... </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">#echo -n message 输出结果后不换行 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">echo -n &quot;Do you want to continue: Y or N&quot; </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">read ANSWER </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">if [ $ANSWER=N -o $ANSWER=n ] </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">then </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">exit </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">fi </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">i. case结构：结构较elif-then结构更清楚 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">比较if-then语句： </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">if [ variable1 = value1 ] </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">then </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">command </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">command </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">elif [ variable1 = value2 ] </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">then </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">command </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">command </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">elif [ variable1 = value3 ] </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">then </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">command </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">command </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">fi </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">相应的case结构： </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">case value in </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">pattern1) </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">command </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">command;; </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">pattern2) </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">command </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">command;; </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">... </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">patternn) </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">command; </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">esac </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">* case语句只执行第一个匹配模式 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">例：使用case语句建立一个菜单选择shell script </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">#Display a menu </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">echo _ </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">echo &quot;1 Restore&quot; </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">echo &quot;2 Backup&quot; </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">echo &quot;3 Unload&quot; </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">echo </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">#Read and excute the user's selection </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">echo -n &quot;Enter Choice:&quot; </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">read CHOICE </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">case &quot;$CHOICE&quot; in </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">1) echo &quot;Restore&quot;;; </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">2) echo &quot;Backup&quot;;; </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">3) echo &quot;Unload&quot;;; </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">*) echo &quot;Sorry $CHOICE is not a valid choice </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">exit 1 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">esac </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">在上例中，*指默认匹配动作。此外，case模式中也可以使用逻辑操作，如下所示： </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">pattern1 | pattern2 ) command </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">command ;; </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">这样可以将上面示例程序中允许用户输入数字或每一个大写字母。 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">case &quot;$CHOICE&quot; in </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">1|R) echo &quot;Restore&quot;;; </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">2|B) echo &quot;Backup&quot;;; </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">3|U) echo &quot;Unload&quot;;; </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">*) echo &quot;Sorry $CHOICE is not a valid choice </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">exit 1 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">esac </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">(5)循环控制 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">&lt;1&gt; while循环: </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">格式： </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">while command </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">do </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">command </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">command </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">command </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">... </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">done </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">例： 计算1到5的平方 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">#!/bin/sh </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left"># </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">#Filename: square.sh </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">int=1 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">while [ $int -le 5 ] </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">do </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">sq=`expr $int \* $int` </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">echo $sq </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">int=`expr $int + 1` </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">done </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">echo &quot;Job completed&quot; </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">$ sh square.sh </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">1 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">4 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">9 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">16 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">25 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">Job completed </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">&lt;2&gt; until循环结构： </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">格式： </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">until command </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">do </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">command </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">command </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">.... </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">command </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">done </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">示例：使用until结构计算1-5的平方 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">#!/bin/sh </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">int=1 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">until [ $int -gt 5 ] </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">do </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">sq=`expr $int \* $int` </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">echo $sq </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">int=`expr $int + 1` </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">done </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">echo &quot;Job completed&quot; </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">&lt;3&gt; 使用shift对不定长的参数进行处理 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">在以上的示例中我们总是假设命令行参数唯一或其个数固定，或者使用$*将整个命令 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">行参数传递给shell script进行处理。对于参数个数不固定并且希望对每个命令参数 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">进行单独处理时则需要shift命令。使用shift可以将命令行位置参数依次移动位置， </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">即$2-&gt;$1, $3-&gt;$2. 在移位之前的第一个位置参数$1在移位后将不在存在。 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">示例如下： </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">#!/bin/sh </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left"># </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">#Filename: shifter </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">until [ $# -eq 0 ] </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">do </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">echo &quot;Argument is $1 and `expr $# - 1` argument(s) remain&quot; </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">shift </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">done </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">$ shifter 1 2 3 4 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">Argument is 1 and 3 argument(s) remain </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">Argument is 2 and 2 argument(s) remain </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">Argument is 3 and 1 argument(s) remain </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">Argument is 4 and 0 argument(s) remain </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">$ </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">使用shift时，每进行一次移位，$#减1，使用这一特性可以用until循环对每个参 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">数进行处理，如下示例中是一个求整数和的shell script: </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">#!/bin/sh </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left"># sumints - a program to sum a series of integers </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left"># </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">if [ $# -eq 0 ] </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">then </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">echo &quot;Usage: sumints integer list&quot; </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">exit 1 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">fi </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">sum=0 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">until [ $# -eq 0 ] </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">do </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">sum=`expr $sum + $1` </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">shift </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">done </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">echo $sum </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">$ sh sumints 324 34 34 12 34 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">438 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">$ </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">使用shift的另一个原因是Bourne Shell的位置参数变量为$1~$9, 因此通过位置变量 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">只能访问前9个参数。但这并不等于在命令行上最多只能输入9个参数。此时如果想访问 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">前9个参数之后的参数，就必须使用shift. </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">另外shift后可加整数进行一次多个移位，如： </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">shift 3 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">&lt;4&gt;. for循环 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">格式： </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">for var in arg1 arg2 ... argn </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">do </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">command </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">.... </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">command </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">done </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">示例： </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">$ for letter in a b c d e; do echo $letter;done </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">a </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">b </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">c </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">d </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">e </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">对当前目录下的所有文件操作： </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">$ for i in * </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">do </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">if [ -f $i ] </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">then </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">echo &quot;$i is a file&quot; </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">elif [ -d $i ] </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">echo &quot;$i is a directory&quot; </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">fi </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">done </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">求命令行上所有整数之和： </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">#!/bin/sh </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">sum=0 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">for INT in $* </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">do </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">sum=`expr $sum + $INT` </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">done </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">echo $sum </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">&lt;6&gt; 从循环中退出： break和continue命令 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">break 立即退出循环 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">continue 忽略本循环中的其他命令，继续下一下循环 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">在shell编程中有时我们要用到进行无限循环的技巧，也就是说这种循环一直执行碰 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">到break或continue命令。这种无限循环通常是使用true或false命令开始的。UNIX </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">系统中的true总是返加0值，而false则返回非零值。如下所示： </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">#一直执行到程序执行了break或用户强行中断时才结束循环 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">while true </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">do </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">command </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">.... </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">command </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">done </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">上面所示的循环也可以使用until false, 如下： </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">until false </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">do </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">command </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">.... </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">command </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">done </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">在如下shell script中同时使用了continue,break以及case语句中的正规表达式用法： </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">#!/bin/sh </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left"># Interactive program to restore, backup, or unload </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left"># a directory </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">echo &quot;Welcome to the menu driven Archive program&quot; </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">while true </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">do </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left"># Display a Menu </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">echo </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">echo &quot;Make a Choice from the Menu below&quot; </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">echo _ </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">echo &quot;1 Restore Archive&quot; </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">echo &quot;2 Backup directory&quot; </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">echo &quot;3 Unload directory&quot; </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">echo &quot;4 Quit&quot; </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">echo </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left"># Read the user's selection </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">echo -n &quot;Enter Choice: &quot; </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">read CHOICE </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">case $CHOICE in </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">[1-3] ) echo </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left"># Read and validate the name of the directory </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">echo -n &quot;What directory do you want? &quot; </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">read WORKDIR </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">if [ ! -d &quot;$WORKDIR&quot; ] </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">then </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">echo &quot;Sorry, $WORKDIR is not a directory&quot; </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">continue </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">fi </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left"># Make the directory the current working directory </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">cd $WORKDIR;; </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">4) :;; # :为空语句，不执行任何动作 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">*) echo &quot;Sorry, $CHOICE is not a valid choice&quot; </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">continue </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">esac </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">case &quot;$CHOICE&quot; in </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">1) echo &quot;Restoring...&quot; </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">cpio -i </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">2) echo &quot;Archiving...&quot; </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">ls | cpio -o &gt;/dev/rmt/0h;; </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">3) echo &quot;Unloading...&quot; </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">ls | cpio -o &gt;/dev/rmt/0h;; </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">4) echo &quot;Quitting&quot; </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">break;; </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">esac </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">#Check for cpio errors </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">if [ $? -ne 0 ] </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">then </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">echo &quot;A problem has occurred during the process&quot; </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">if [ $CHOICE = 3 ] </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">then </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">echo &quot;The directory will not be erased&quot; </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">fi </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">echo &quot;Please check the device and try again&quot; </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">continue </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">else </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">if [ $CHOICE = 3 ] </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">then </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">rm * </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">fi </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">fi </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">done </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">(6)结构化编程：定义函数 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">同其他高级语言一样，shell也提供了函数功能。函数通常也称之为子过程(subroutine), </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">其定义格式如下： </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">funcname() </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">{ </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">command </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">... </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">command; #分号 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">} </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">定义函数之后，可以在shell中对此函数进行调用，使用函数定义可以将一个复杂的程序分 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">为多个可管理的程序段，如下所示： </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left"># start program </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">setup () </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">{ command list ; } </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">do_data () </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">{ command list ; } </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">cleanup () </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">{ command list ; } </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">errors () </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">{ command list ; } </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">setup </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">do_data </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">cleanup </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left"># end program </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">技巧： </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">. 在对函数命名时最好能使用有含义的名字，即函数名能够比较准确的描述函数所完成 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">的任务。 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">. 为了程序的维护方便，请尽可能使用注释 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">使用函数的另一个好处就是可以在一个程序中的不同地方执行相同的命令序列(函数), </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">如下所示： </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">iscontinue() </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">{ </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">while true </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">do </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">echo -n &quot;Continue?(Y/N)&quot; </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">read ANSWER </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">case $ANSWER in </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">[Yy]) return 0;; </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">[Nn]) return 1;; </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">*) echo &quot;Answer Y or N&quot;;; </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">esac </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">done </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">} </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">这样可以在shell编程中调用iscontinue确定是否继续执行： </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">if iscontinue </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">then </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">continue </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">else </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">break </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">fi </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">** shell函数与shell程序非常相似，但二者有一个非常重要的差别：shell程序是由子shell </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">执行的，而shell函数则是作为当前shell的一部分被执行的，因此在当前shell中可以改 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">变函数的定义。此外在任意shell(包括交互式的shell)中均可定义函数，如： </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">$ dir </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">dir: not found </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">$ dir () { ls -l ;} </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">$ dir </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">total 5875 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">-rw-r--r-- 1 hbwork 100 Nov 10 23:16 doc </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">-rw-r--r-- 1 hbwork 2973806 Nov 10 23:47 ns40docs.zip </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">-rw-r--r-- 1 hbwork 1715011 Nov 10 23:30 ns840usr.pdf </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">-rw-r--r-- 1 hbwork 1273409 Sep 23 1998 radsol21b6.tar.Z </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">-rw-r--r-- 1 hbwork 7526 Nov 10 23:47 wget-log </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">-rw-r--r-- 1 hbwork 1748 Nov 13 21:51 wget-log.1 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">$ unset dir </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">$ dir () { </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">&gt; echo &quot;Permission Link Owner Group File_SZ LastAccess FileName&quot; </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">&gt; echo &quot;-----------------------------------------------------------&quot; </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">&gt; ls -l $*; </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">&gt; } </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">$ dir </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">Permission Link Owner Group File_SZ LastAccess FileName </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">----------------------------------------------------------- </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">total 5875 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">-rw-r--r-- 1 hbwork 100 Nov 10 23:16 doc </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">-rw-r--r-- 1 hbwork 2973806 Nov 10 23:47 ns40docs.zip </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">-rw-r--r-- 1 hbwork 1715011 Nov 10 23:30 ns840usr.pdf </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">-rw-r--r-- 1 hbwork 1273409 Sep 23 1998 radsol21b6.tar.Z </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">-rw-r--r-- 1 hbwork 7526 Nov 10 23:47 wget-log </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">-rw-r--r-- 1 hbwork 1748 Nov 13 21:51 wget-log.1 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">通常情况下，shell script是在子shell中执行的，困此在此子shell中对变量所作的 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">修改对父shell不起作用。点(.) 命令使用shell在不创建子shell而由当前shell读取 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">并执行一个shell script, 可以通过这种方式来定义函数及变量。此外点(.)命令最 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">常用的功能就是通过读取.profile来重新配置初始化login变量。如下所示： </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">$ . .profile </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">(csh相对于.命令的是source命令). </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">(7)使用And/Or结构进行有条件的命令执行 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">&lt;1&gt; And , 仅当第一个命令成功时才有执行后一个命令,如同在逻辑与表达式中如果前面的 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">结果为真时才有必要继续运算，否则结果肯定为假。 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">格式如下： </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">command1 &amp;&amp; command2 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">例：rm $TEMPDIR/* &amp;&amp; echo &quot;File successfully removed&quot; </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">等价于 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">if rm $TEMPDIR/* </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">then </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">echo &quot;File successfully removed&quot; </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">fi </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">&lt;2&gt;Or, 与AND相反，仅当前一个命令执行出错时才执行后一条命令 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">例： rm $TEMPDIR/* || echo &quot;File not removed&quot; </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">等价与： </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">if rm $TEMPDIR/* </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">then </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">command </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">else </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">echo &quot;File not removed&quot; </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">fi </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">&lt;3&gt; 混合命令条件执行 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">command1 &amp;&amp; command2 &amp;&amp; command3 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">当command1, command2成功时才执行command3 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">command1 &amp;&amp; command2 || comamnd3 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">仅当command1成功，command2失败时才执行command3 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">当然可以根据自己的需要进行多种条件命令的组合，在此不多讲述。 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">(8) 使用getopts命令读取unix格式选项 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">UNIX格式选项指如下格式的命令行参数： </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">command -options parameters </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">使用格式： </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">getopts option_string variable </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">具体使用方法请参考getopts的在线文档(man getopts). </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">示例如下： </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">#newdate </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">if [ $# -lt 1 ] </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">then </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">date </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">else </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">while getopts mdyDHMSTjJwahr OPTION </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">do </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">case $OPTION </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">in </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">m) date '+%m ';; # Month of Year </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">d) date '+%d ';; # Day of Month </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">y) date '+%y ';; # Year </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">D) date '+%D ';; # MM/DD/YY </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">H) date '+%H ';; # Hour </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">M) date '+%M ';; # Minute </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">S) date '+%S ';; # Second </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">T) date '+%T ';; # HH:MM:SS </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">j) date '+%j ';; # day of year </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">J) date '+%y%j ';;# 5 digit Julian date </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">w) date '+%w ';; # Day of the Week </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">a) date '+%a ';; # Day abbreviation </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">h) date '+%h ';; # Month abbreviation </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">r) date '+%r ';; # AM-PM time </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">\?) echo &quot;Invalid option $OPTION&quot;;; </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">esac </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">done </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">fi </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">$ newdate -J </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">94031 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">$ newdate -a -h -d </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">Mon </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">Jan </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">31 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">$ newdate -ahd </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">Mon </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">Jan </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">31 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">$ </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">示例程序：复制程序 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left"># Syntax: duplicate [-c integer] [-v] filename </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left"># where integer is the number of duplicate copies </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left"># and -v is the verbose option </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">COPIES=1 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">VERBOSE=N </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">while getopts vc: OPTION </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">do </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">case $OPTION </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">in </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">c) COPIES=$OPTARG;; </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">v) VERBOSE=Y;; </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">\?) echo &quot;Illegal Option&quot; </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">exit 1;; </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">esac </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">done </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">if [ $OPTIND -gt $# ] </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">then </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">echo &quot;No file name specified&quot; </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">exit 2 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">fi </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">shift `expr $OPTIND -1` </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">FILE=$1 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">COPY=0 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">while [ $COPIES -gt $COPY ] </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">do </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">COPY=`expr $COPY + 1` </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">cp $FILE ${FILE}${COPY} </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">if [ VERBOSE = Y ] </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">then </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">echo ${FILE}${COPY} </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">fi </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">done </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">$ duplicate -v fileA </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">fileA1 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">$ duplicate -c 3 -v fileB </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">fileB1 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">fileB2 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">fileB3 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">4. Shell的定制 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">通常使用shell的定制来控制用户自己的环境，比如改变shell的外观(提示符)以及增强 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">自己的命令。 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">(1)通常环境变量来定制shell </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">通常改变环境变量可以定制shell的工作环境。shell在处理信息时会参考这些环境变量 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">，改变环境变量的值在一定程度上改变shell的操作方式，比如改变命令行提示符。 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">.使用IFS增加命令行分隔符 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">默认状态下shell的分隔符为空格、制表符及换行符，但可以通过改变IFS的值加入自己 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">的分隔符。如下所示： </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">$ IFS=&quot;:&quot; </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">$ echo:Hello:my:Friend </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">Hello my Friend </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">(2)加入自己的命令及函数 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">如下程序： </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">#Directory and Prompt change program </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">#Syntax: chdir directory </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">if [ ! -d &quot;$1&quot; ] </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">then </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">echo &quot;$1 is not a directory&quot; </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">exit 1 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">fi </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">cd $1 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">PS1=`pwd`$ </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">export PS1 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">$ chdir /usr/home/teresa </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">$ </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">但此程序在执行时系统提示符并不会改变，因为此程序是在子shell中执行的。因此其变量 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">对当前shell并无影响，要想对当前shell起作用，最好是将此作为函数写在自己的.profile中 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">或建立自己的个人函数文件.persfuncs </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">#Personal function file persfuncs </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">chdir() </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">{ </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">#Directory and Prompt change program </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">#Syntax: chdir directory </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">if [ ! -d &quot;$1&quot; ] </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">then </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">echo &quot;$1 is not a directory&quot; </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">exit 1 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">fi </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">cd $1 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">PS1=`pwd`$ </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">export PS1; </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">} </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">再执行： </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">$ . .persfuncs </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">$ chdir temp </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">/home/hbbwork/temp$ </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">也可在自己的.profile文件中用 . .persfuncs调用.persfuncs. </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">说明：在bash/tcsh中已经使用别名，相对而言别名比此方法更为方便。 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">5. 有关shell的专门讨论 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">(1)shell程序的调试 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">切记：程序员（人）总是会犯错误的，而计算机是不会错的。 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">使用-x进行跟踪执行，执行并显示每一条指令。 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">(2)命令组 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">用小括号将一组命令括起来，则这些命令会由子shell来完成；而{command_list;}则在当 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">前shell中执行。这两者的主要区别在于其对shell变量的影响，子shell执行的命令不会 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">影响当前shell中的变量。 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">$ NUMBER=2 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">$ (A=2;B=2;NUMBER=`expr $A + $B`; echo $NUMBER) </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">4 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">$ echo $NUMBER </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">2 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">$ { A=2;B=2;NUMBER=`expr $A + $B`; echo $NUMBER; } </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">4 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">$ echo $NUMBER </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">4 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">总结：</span><span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left"> </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">在本章中讲述了Bourne Shell的基本知识,使用shell变量，shell script基础。这些概念对于理解学习Korn Shell, csh以及其他script编程都是非常有用的。 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">很多OS都有不少语言及一些script功能，但很少有象UNIX SHELL这样灵活强大的script脚本语言能力。 </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">对于系统管理员或程序员来说，熟练地使用shell script将对日常工作(系统维护及管理) 非常有用，如果你想作一个合格的系统管理员，强烈建议你进一步深入的了解和使用shell. </span><br style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left" />
<span style="font-family:Helvetica,Tahoma,Arial,sans-serif; font-size:14px; line-height:25px; text-align:left">另外，对于系统管理员来说，PERL也是一个必不可少的script编程语言，尤其是对于处理文本格式的各种文件，PERL具有shell, awk, sed, grep等的功能，但使用起来更为灵活，功能也更强大。大家可以参考“Perl By Examples&quot;来学习和使用PERL</span>
