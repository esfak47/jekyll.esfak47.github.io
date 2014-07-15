---
layout: post
title:  "Basic commands of Tcl"
date:   2014-07-14 22:31:00
categories: Tcl
img_src: "/img/tcl.jpg"
description: "Help you learning tcl quickly."
---
## Tcl 学习之路
###变量
- tcl变量在初始化的时候无类型
- 使用set xxx = xxxx进行初始化
- 使用set xxx可以查看xxx的值
- 使用unset将变量release掉
- 预定义的变量包括env（系统变量）argv（脚本执行的参数）argc（脚本参数的个数）argv0执行脚本的程序名


###【】的使用
- 【】用于将内部命令结果的返回值作为另外一个命令的参数
- 比如 set var2 【set var】就把var的只传给了var2

###“”的使用
- 用于把一段内容封装成string类型
- 比如 set var "multiple word"
- 可以在“”中加入【】之类进行替换
- 比如 set b "a is [set a]" 会打印a is 2
- 特殊字符如\n等同样有效

###{}的使用
- 如果内容内部不需要对特殊字符进行处理，那么可以使用{}
- 如set a {123\n},则不会对\n进行处理

###数组
set earnings(January) 87966
注意tcl中的array是基于map形式的，没有固定的元素顺序，需要顺序的话可以使用列表，这里的数组有点像java中的set，索引始终是字符串类型的，即使你使用1作为索引，他依然是将1转换成字符串
###多维数组
- 可以通过多个索引实现多维数组
- 例如set matrix（1,1）140

###查询数组元素
{% highlight tcl %}
set currency(Frence) euro
set currency(Britain) pound
set currency(Japan) yen
array size currency
# =>3
array names currency
# => Britain Japan Frence
foreach i [array names currency] {
	puts currency($i)
}
# => pound yen euro
{% endhighlight %}
###列表
{% highlight tcl %}
set a {1 2 3 4}
lindex $a 2
#=> 2
set a [list a b c d e f g]
lindex $a 2
#=> b
#concat ?arg arg ...?
#使用多个arg来组成一个列表，这两个命令使用频度很高，使用也非常简单
{% endhighlight %}
###字符串操作
{% highlight tcl %}
string length string
#返回String中的字符串个数
string range string first last
#返回string当中从first到last之间的所有子字符串
string match ?-nocase? pattern string
#尝试对string进行匹配，匹配成功返回1，否则返回0
string relace string first last ？newstring？
#尝试将frist到last中间所有字符串替换为newstring
string trim string
#尝试删除string前后的空格
string compare string1 string2
#尝试比较string1和string2
string is digit 1234
#返回1234是否为数字
{% endhighlight %}
###正则表达式
{% highlight tcl %}
regex {^[0-9]+$} 510
#尝试对后面的字符串进行匹配，若匹配成功返回1，否则返回0
regex {([0-9]+) *([a-z]+)}
{% endhighlight %}
