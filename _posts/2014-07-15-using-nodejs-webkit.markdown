---
layout: post
title: "Using nodejs to develop desktop app"
date: 2014-07-15 22:31:00
categories: nodejs
img_src: "/img/nodejs.jpg"
description: "Using nodejs to develop desktop app"
---

# 目录 #

### 一、node-webkit是什么？ ###

### 二、node-webkit有些什么干货？ ###

### 三、node-webkit的基本工作原理是怎样的？ ###

### 四、怎样用node-webkit进行客户端开发？ ###

### 五、如何做到开发一份代码，生成多平台APP？ ###

### 六、使用node-webkit开发桌面客户端的优缺点？ ###

### 七、Q & A! ###

 

### 一、node-webkit是什么？ ###

#### 1、概念 ####

基于node.js和chromium的应用程序实时运行环境，可运行通过HTML(5)、CSS(3)、Javascript来编写的本地应用程序。node.js和webkit的结合体，webkit提供DOM操作，node.js提供本地化操作；且将二者的context完全整合，可在HTML代码中直接使用node.js的API。

 

#### 2、获取node-webkit ####

官网：[https://github.com/rogerwang/node-webkit](https://github.com/rogerwang/node-webkit)

支持的平台：Windows 32bit，Linux 32/64bit，Mac 32bit(OS X 10.7+)

选择与平台相对应的版本，下载并安装即可。

 

### 二、node-webkit有些什么干货？ ###

官方提供的一些成品：[https://github.com/rogerwang/node-webkit/wiki/List-of-apps-and-companies-using-node-webkit](https://github.com/rogerwang/node-webkit/wiki/List-of-apps-and-companies-using-node-webkit)

 

### 三、node-webkit的基本工作原理是怎样的？ ###

webkit提供DOM操作，包括HTML解析、CSS渲染、Javascript解释执行、DOM事件处理等。而node.js则提供一些本地化的操作、服务器端的处理等。二者的上下文完全融合，实现一个较为完美的本地应用环境。

 

### 四、怎样用node-webkit进行客户端开发？ ###

#### 1、一个node-webkit项目的基本目录结构 ####

上面这是一个简单nw应用的目录结构，如果nw应用中需要用到额外的node_module，可以在目录结构中增加一个node_modules的目录，以存放APP所需的node插件。

其实，一个最最简单的nw应用，只需要有mail.html和package.json文件即可，如下：

 

#### 2、认识package.json ####

“Every app package should contain a manifest file named package.json, it will tell node-webkit how to open the app and control how the browser behaves. ”

package.json格式如下：
{% highlight json %}
{
    "main": "main.html",                              /* APP的主入口，文件名任意；必选 */
    "name": "nw-demo",                                /* APP的名称，必须具备唯一性，且符合正常变量命名；必选 */
    "description": "demo app of node-webkit",         /* APP的简单描述 */
    "version": "0.1.0",                               /* APP的版本号 */
    "keywords": [ "demo", "node-webkit" ],            /* APP的关键字，搜索APP时用到 */
    "window": {                                       /* APP的窗口属性 */
        "icon": "link.png",                           /* APP图标（windows下，状态栏上可见） */
        "toolbar": true,                              /* 是否显示工具栏 */
        "width": 800,                                 /* 窗口初始化大小 */
        "height": 500,
        "frame": true                                 /* 是否显示外窗体，如最大化、最小化、关闭按钮 */
    },
    "user-agent": "%name %ver %nwver %webkit_ver %osinfo" /* 可自定义APP的UA */
}
{% endhighlight %}
 


其中，main和name是必选字段，更多配置字段，可参考官方地址：[https://github.com/rogerwang/node-webkit/wiki/Manifest-Format](https://github.com/rogerwang/node-webkit/wiki/Manifest-Format)

#### 3、主窗口mail.html的写法 ####

随意写，和普通的前端页面开发方式一样！

#### 4、最简单的HelloWorld ####


Create `index.html`:

{% highlight html %}
<!DOCTYPE html>
<html>
  <head>
    <title>Hello World!</title>
  </head>
  <body>
    <h1>Hello World!</h1>
    We are using node.js <script>document.write(process.version)</script>.
  </body>
</html>
{% endhighlight %}

Create `package.json`:

{% highlight json %}
{
  "name": "nw-demo",
  "main": "index.html"
}
{% endhighlight %}

Compress `index.html` and `package.json` into a zip archive called `app.nw`:

{% highlight bash %}
$ zip app.nw index.html package.json
{% endhighlight %}

This should create a structure like this:

```
app.nw
|-- package.json
`-- index.html
```

Download the prebuilt binary for your platform and use it to open the
`app.nw` file:

{% highlight bash %}
$ ./nw app.nw
{% endhighlight %}

也许你会觉得这个界面特别熟悉，没错，它就是chromium！只是在node-webkit中，我们可以通过修改package.json配置，把工具栏和外框去掉，修改后的配置为：

去掉外框后的运行效果：

你一定会发现去掉toolbar和frame以后，窗口没法被拖动了，其实，可以通过下面这句css来实现窗口可拖动：

 

### 五、如何做到开发一份代码，生成多平台APP？ ###

#### 1、nw包制作 ####

完成上面的操作，已经生成了一个名为hello-world.nw的文件，如果本机已经安装过node-webkit，双击该文件即可运行。但是，针对未安装过node-webkit的用户，还需要将此nw的运行环境也打包在一起，并生成通用可执行文件，Mac上*.app，Windows上*.exe。

 

#### 2、针对Mac OS X，*.app文件制作 ####

a）、app.icns文件制作

为你的App制作特定图标，可准备一张1024*1024的png图片，利用icns-Tool工具生成app.icns图标文件。

b）、修改Info.plist文件

为你的App制作或修改特定的描述文件。

c）、打包*.app

从官网再次下载node-webkit的Mac版，命令行执行：
{% highlight bash %}
mv hello-world.nw app.nw 
cp app.nw node-webkit.app/Contents/Resources/
cp app.icns node-webkit.app/Contents/Resources/
cp Info.plist node-webkit.app/Contents/
mv node-webkit.app hello-wrold.app
{% endhighlight %}
至此，Mac OS X版本的可执行程序hello-world.app制作完成。

一般情况下，都会将其压缩后再进行传播。

#### 3）、针对Windows，*.exe文件制作 ####

windows版本的exe程序制作非常容易，从官网下载node-webkit.exe，cmd下执行：
{% highlight bat %}

copy /b node-webkit.exe+app.exe hello-world.exe
{% endhighlight %}
在Linux环境下，可以使用如下命令：
{% highlight bash %}

cat node-webkit.exe app.exe > hello-world.exe
{% endhighlight %}
至此，Windows版本的hello-world.exe程序制作完成。

 

4）、将繁琐重复的操作整合到一个build.sh脚本中
{% highlight bash %}
#! sh
app_name="system-info"
# 创建app.nw文件
cd ../ && rm -rf output && mkdir output cp
rm -rf output
-r $app_name/* output
rm -rf output/Info.plist output/build.sh output/app.icns
cd output/
find . -type d -name ".svn" | xargs rm -rf
zip -r ../app.nw * > /dev/null;
rm -rf * && cd ../ && mv app.nw output/
mv output $app_name/ && cd $app_name
echo "create nw file success!"

#下载基础包
svn co svn://localhost/node-webkit-base output > /dev/null

#创建mac版本app
cd output
unzip mac-os-x.zip -d mac-os-x > /dev/null
rm -rf mac-os-x.zip mac-os-x/nwsnapshot
if [ -f ../Info.plist ];then
cp ../Info.plist mac-os-x/node-webkit.app/Contents/
fi
cp app.nw mac-os-x/node-webkit.app/Contents/Resources/
if [ -f ../app.icns ];then
cp ../app.icns mac-os-x/node-webkit.app/Contents/Resources/
fi
mv mac-os-x/node-webkit.app mac-os-x/$app_name.app
echo "create mac os app success!"

#创建windows版本app
unzip win-32.zip -d win-32 > /dev/null
rm -rf win-32.zip win-32/nwsnapshot
cp app.nw win-32/ && cd win-32
cat nw.exe app.nw > $app_name.exe
rm -rf nw.exe nwsnapshot.exe
cd ..
echo "create windows app success!"

#删除app.nw
rm -f app.nw
{% endhighlight %}
 

### 六、使用node-webkit开发桌面客户端的优缺点？ ###

1、优点

- 提高UI开发效率，DOM中丰富的事件等可以涵盖绝大多数桌面开发中的情况
- HTML(5)与CSS(3)拥有丰富的展现效果，可以更容易地对界面进行改版、换肤
- 容易实现跨平台:Mac OS X 、Windows、Linux
- 使用Web开发人员工具可以使 UI 调试变得很轻松
- 桌面程序UI与Web版UI可以共享代码

2）、缺点

- 浏览器原生API几乎仅仅局限在Web页面上
- 若通过JavaScript引擎向Web前端暴露一些具有操作客户端权限的API，如何保证代码安全性
- 必须携带浏览器内核运行库，无形增加程序体积，至少20MB以上（压缩后）
- 能否满足各种复杂怪异的需求，比如异型窗口

