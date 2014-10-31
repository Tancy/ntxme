---
layout: post
title:  "Charles 基础篇"
description: Charles是目前最强大的http调试工具之一，本片讲述Charles的基础篇，介绍软件的基本界面，设置和使用方法。
category: blog
---


Charles是目前最强大的http调试工具之一，在界面和功能上远强于Fiddler，同时是全平台支持，堪称神器，唯一的缺陷是这软件是收费的，而且是要$50美金…
<div>
    <img style="width: 100%;" src="http://gtms01.alicdn.com/tps/i1/TB1kJ5uFVXXXXXAXpXXrJ1vVXXX-1304-621.png" alt="Charles 启动画面">
</div>
启动后，神器启动画面。
<div>
    <img style="width: 100%;" src="http://gtms03.alicdn.com/tps/i3/TB1HYmwFVXXXXcLXXXXZBIoIVXX-2246-1300.png" alt="Charles 主界面">
</div>
神器主界面。
Charles有个会话（session，不是指http中的session）的概念，可以理解为浏览器中的tab，这个功能在需要调试多个站点页面时很实用，当你刷新页面的时候，只会在当前session中捕获请求。
（PS：MacOS 下command+N创建个新的session，command+W关闭当前session）
Charles的代理服务器启动就可以使用（会提示给firefox安装插件），如果没有捕获到请求，请清理下浏览器缓存。

##界面功能初探

<div>
    <img style="width: 100%;" src="http://gtms04.alicdn.com/tps/i4/TB1E4CyFVXXXXXMXXXXOh7JIVXX-2246-1444.png" alt="Charles 界面功能概览"/>
</div>
工具条包含了Charles的大部分功能：
<div>
    <img style="width: 100%;" src="http://gtms02.alicdn.com/tps/i2/TB1o9ayFVXXXXb0XXXXl47zIVXX-2246-1360.png" alt="Charles 界面功能概览"/>
</div>

有几个功能比较抽象，后面会详细说明。
右键请求出现菜单，Charles的右键菜单功能比fiddler强大太多了。
<div>
    <img style="width: 100%;" src="http://gtms01.alicdn.com/tps/i1/TB1iD1rFVXXXXasXFXXiAt_5pXX-642-1234.png" alt="Charles 快捷菜单"/>
</div>
双击请求进入列表视图，类似fiddler，方便查看和过滤请求。
<div>
    <img style="width: 100%;" src="http://gtms03.alicdn.com/tps/i3/TB1XIKfFVXXXXcGaXXXn577ZVXX-2188-1428.png" alt="Charles 搜索&详情"/>
</div>
Charles的过滤查找功能非常赞，很快速：请求详情跟fiddler相似，但直观不少：工具视图基本讲解完毕，接下来我们用Charles做点事情。


##代理配置

<div>
    <img style="width: 100%;" src="http://gtms04.alicdn.com/tps/i4/TB1sJimFVXXXXbIXVXX0IBa0pXX-1444-1054.png" alt="Charles 代理设置"/>
</div>


##本地代理和远程代理

Charles的代理服务器端口跟fiddler一样都是8888，即你的本机ip:8888。
<div>
    <img style="width: 100%;" src="http://gtms03.alicdn.com/tps/i3/TB1hZysFVXXXXXFXFXXDLxq5XXX-2254-1432.png" alt="Charles 搜索&详情"/>
</div>


我们可以目标将一个文件代理成本地的文件。点击“Map Local”后：
<div>
    <img style="width: 100%;" src="http://gtms03.alicdn.com/tps/i3/TB1hZysFVXXXXXFXFXXDLxq5XXX-2254-1432.png" alt="Charles Map Local"/>
</div>

刷新页面试试。代理成功，so easy！

Charles的树状视图比fiddler的列表视图好的地方在于，多次刷新后的请求会被归纳到树里面，更加一目了然，用fiddler的时候，有点强迫症的同学，都要点击clear，有木有…
Charles是支持子目录代理哦，非常实用的功能：（使用通配符*）
<div>
    <img style="width: 100%;" src="http://gtms03.alicdn.com/tps/i3/TB1BqiwFVXXXXbmXpXXA3IeJFXX-1246-872.png" alt="Charles 目录代理"/>
</div>

本地地址选择个子目录，不需要通配符。
如何判断是否代理成功呢？
<div>
    <img style="width: 100%;" src="http://gtms03.alicdn.com/tps/i3/TB1aNqsFVXXXXXZXFXXXss1_VXX-2130-1342.png" alt="Charles notes"/>
</div>


这点Charles比fiddler人性化多了。
校验是否代理成功，最省力的方式是点击工具条上的刷新按钮，刷新单个请求，如果代理成功，Charles会往“Notes”界面打个log。

<div>
    <img style="width: 100%;" src="http://gtms02.alicdn.com/tps/i2/TB1LKOsFVXXXXcpXpXXkrcY_VXX-2130-1324.png" alt="Charles notes"/>
</div>
去除代理配置

小技巧：所有的配置开关都可以通过工具条上的“工具”设置（倒数第二个按钮）。

小技巧：建议开启No Caching，不缓存请求。


##mobile代理功能

手机或平板页面的调试，我们需要把请求代理到pc端的Charles上。
必须确保mobile端和pc端连的是相同的无线网络。
ios的配置非常简单
<div>
    <img style="width: 100%;" src="http://gtms04.alicdn.com/tps/i4/TB1Z8WqFVXXXXXiXFXXr6RC8VXX-1280-1136.png" alt="Charles ios网络"/>
</div>

服务器ip设置成pc的ip，端口好设置成8888即可。
然后mobile终端可以刷新试试。

Charles支持https和sockets的代理，还支持SSL，非常全面。
