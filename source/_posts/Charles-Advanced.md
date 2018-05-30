---
layout: post
title:  "Charles 高级篇"
description: 本片讲述Charles的高级篇，介绍软件的网速模拟功能，牛逼的断点功能，重复发送请求，捕获记录控制。
cover_image: images/TB14YKiFVXXXXXPaXXXoKiP5pXX-1644-934.png
categories:
  - Blog
tag:
  - Charles
date: 2014-07-21 19:16:00
---

基础篇讲解了Charles最常用功能代理的使用，高级篇继续演示Charles的特色有趣的功能。

##网速模拟功能

throttle功能对于前端来说非常实用，可以看页面在低网速下的表现，从而找出优化的点。
在线上环境通常有些因为网速慢导致的bug，在本机无法重现，那时候就很抓瞎，如果嫌远程麻烦，推荐使用throttle。

首先先配置下throttle。

<div>
    <img style="width: 100%;" src="http://gtms01.alicdn.com/tps/i1/TB12wOAFVXXXXcmXXXXVcq6YpXX-2124-1384.png" alt="Charles 设置Throttle">
</div>

设置各种网络速率

<div>
    <img style="width: 100%;" src="http://gtms04.alicdn.com/tps/i4/TB1vdqsFVXXXXcoXFXXSByXHVXX-1100-1144.png" alt="Charles 设置Throttle">
</div>
（Charles的预配置对于中国的网络环境并不准确，电信、移动、网通的速度还有有明显差异。）
解析下图上几个配置的含义：
Bandwidth（带宽）、Utilistation（利用百分比）、Round-trip（往返延迟）、MTU（字节）。

##牛逼的断点功能

Charles另一个非常实用的功能，对于开发者和测试人员来说，堪称神器。Charles能够断到发送请求前（篡改Request）和请求后（篡改Response）。

场景：ajax发送请求，我们需要测试接口的各种边界情况，比如出错、超时等表现，Charles的断点+随意篡改，非常方便测试。


针对某一个请求，右键选择“BreakPoints”，开启断点。

<div>
    <img style="width: 100%;" src="http://gtms02.alicdn.com/tps/i2/TB1pb5iFVXXXXaVaXXXEY0C6VXX-2126-1332.png" alt="Charles 设置断点">
</div>

小技巧：不用在web界面中操作，使用repeat功能，就可再次发送一样的请求：

<div>
    <img style="width: 100%;" src="http://gtms01.alicdn.com/tps/i1/TB1tCWyFVXXXXXEXpXXqNZYGFXX-912-670.png" alt="Charles 重新请求">
</div>

###断点列表查看

<div>
    <img style="width: 100%;" src="http://gtms03.alicdn.com/tps/i3/TB1.iylFVXXXXayaXXXJcUmOVXX-2122-1382.png" alt="Charles 断点列表">
</div>

可以指定断点“get”请求还是“post”请求。

##重复发送请求

repeat功能对于测试同学特别有用，可以检验接口的健壮性。
repeat功对于前端的价值是不需要刷新页面，只需要repeat请求，比如检验代理是否成功，修改请求后执行等。
<div>
    <img style="width: 100%;" src="http://gtms01.alicdn.com/tps/i1/TB1tCWyFVXXXXXEXpXXqNZYGFXX-912-670.png" alt="Charles 重复请求">
</div>


“repeat”重复发送一次请求。

“repeat Advances”可以自定义重复次数和重复间隔。
<div>
    <img style="width: 100%;" src="http://gtms02.alicdn.com/tps/i2/TB1hfGpFVXXXXczXFXXI.IF6XXX-1434-956.png" alt="Charles 自定义重复次数和重复间隔">
</div>



##捕获记录控制

捕获的请求太多，容易产生干扰，Charles可以对捕获记录进行过滤。

然后配置“exclude”：
<div>
    <img style="width: 100%;" src="http://gtms03.alicdn.com/tps/i3/TB1SImyFVXXXXcRXXXX6aMrIXXX-2128-1380.png" alt="Charles 记录过滤">
</div>


##web界面

Charles有个有趣的web界面：

<div>
    <img style="width: 100%;" src="http://gtms02.alicdn.com/tps/i2/TB1Jk5pFVXXXXcTXFXXXpwU2VXX-1096-1034.png" alt="Charles 记录过滤">
</div>


强大的是可以控制是否远程可以访问这个界面，还可以设置用户名和密码…碉堡了…

浏览器输入http://control.charles/ ：

<div>
    <img style="width: 100%;" src="http://gtms01.alicdn.com/tps/i1/TB14YKiFVXXXXXPaXXXoKiP5pXX-1644-934.png" alt="Charles 记录过滤">
</div>


Charles还有其他有趣功能等待大家挖掘...