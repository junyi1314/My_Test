Query EasyUI 引用加载方式分析

easyui是什么，就不介绍了，接触到前端的就算没用过，肯定也应该听说过。其次，本文不是介绍它提供如calendar、tree等这些功能如何使用的，这些官网上介绍都很详细，中文的网上也不少。本文是从easyui的文件目录结构上来说起，谈一下easyui的两种引用加载方式。

 

引用加载方式
easyui的加载可以分为两种方式，方式一：饿汉式加载；2：懒汉式加载。在具体讨论这两种加载方式之前，我们先看下easyui目录结构。

 

目录结构
demo文件夹：一些示例，（正式项目中删除）

locale：一些不同语言的文件，其实是对easyui的扩展。（只须保留你想用的语言相对应的文件）

plugins：easyui提供的各个功能的文件。（使用方式二加载必须保留，方式一加载可以删除）

src :各个插件的源文件，不是全部，其实有些功能不是开源的，是商业授权，因此没有源文件。（可以删除）

themes：主题，就是css文件和要用到的图标文件，里边提供5种风格。（可以只保留要使用的风格，并且具体到一个风格里，又分为两部分：easyui.css和其它所有css。easyui.css是其它所有css的合并后结果，在不同的加载方式中只会用到一部分。）

easyloader.js：暂且称之为加载器文件。在使用方式一加载也不会被使用。

jquery.easyui.min.js：easyui的主文件。它是plugins下所有文件合并后的结果，因些它在使用方式一加载必须保留，方式二加载不会使用到，可以删除（主文件可以删除，没听错吧？？哈哈，相信我，可以的。）。

jquery.min.js：jquery文件，easyui是基于jquery的，因此是必须的。

 

其它的是一些授权文件和更新日志之类的，就不说了。

 

这里有两个重点：jquery.easyui.min.js是plugins下所有文件合并后的结果，具体到某个风格下如default下所有css：easyui.css是余下的其它所有css合并之后的结果。

这样就导致了不同的两种加载方式。

 

饿汉式加载
<link rel="stylesheet" type="text/css" href="easyui/themes/default/easyui.css">
<link rel="stylesheet" type="text/css" href="easyui/themes/icon.css">
<script type="text/javascript" src="easyui/jquery.min.js"></script>
<script type="text/javascript" src="easyui/jquery.easyui.min.js"></script>
这种也是最常用的方式。这种方式会加载easyui提供的所有功能，不管你页面上会不会用的到，简单暴力。

 

懒汉式加载
<link rel="stylesheet" type="text/css" href="easyui/themes/icon.css">
<script type="text/javascript" src="easyui/jquery.min.js"></script>
<script type="text/javascript" src="easyui/jquery.easyloader.js"></script>
这种方式就相对比较懒，只会在使用特定功能的时候才会加载相对应的plugins下的js和风格里css文件，而其它不使用的功能对应的js和css永远不会被下载。而easyloader.js就是负责用于加载各个插件的。

 

调用
同样，都是两种使用方式，我们这里只讨论下在方式2调用过程。

当页面中包含如：

<a href="#" class="easyui-linkbutton" onclick="load1()">Load Calendar</a>
html标记中class指定easyui-linkbutton之类easyui特定的标记时，easyui会检测到并自动的去下载相对应的文件，并应用相应的样式和功能。对于easyui-linkbutton标记就是去下载themes/default/linkbutton.css和plugins/jquery.linkbutton.js这两个文件，然后改变a的显示样式。

 

当然我们可以手动通过js去调用相关功能：

using('calendar', function(){
                $('#cc').calendar({
                    width:180,
                    height:180
                });
            });
这样就会去加载calendar对就的css和js文件，并在id为cc的div上创建一个日历控件。

 

问题
很快，我们就会发现一些问题。

 

风格
方式1的加载我们通过引用 themes/default/easyui.css来指定，引用不同风格下的easyui.css来使用不同的风格，但是方式2我们并没用指定风格？如何指定风格？

不指定时，默认是引用default风格下的样式，就会去下载该风格下的样式。如果你使用方式2时且没有指定风格，不存在default风格就会出现问题。

当然我们可以在页面加载后通过

easyloader.theme = "gray";
来指定风格。

 

语言
同样的对于语言文件，对于方式1我们可以直接在页面引用jquery.easyui.min.js的后面引用。

<script type="text/javascript" src="easyui/locale/easyui-lang-zh_CN.js"></script>
但是这对于方式2的加载，这是不起作用的。

因些语言文件其实是对各个插件默认配置的修改，当插件都还没有加载时，语言文件对它的修改当然是不会起作用的。

因此我们可以通过下面

easyloader.locale = "zh_CN";
来指定使用何种语言。