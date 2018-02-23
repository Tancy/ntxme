---
layout: post
title:  "Charles 之SSL"
description: 本片讲述Charles的高级篇，介绍软件特色功能之SSL。
cover_image: //gtms01.alicdn.com/tps/i1/TB1kJ5uFVXXXXXAXpXXrJ1vVXXX-1304-621.png
categories:
  - Blog
tag:
  - Charles
  - SSL
date: 2014/07/22 20:16:00
---

本次高级篇继续演示Charles的特色功能之SSL。

##启用SSL Proxy

现在我们已启动一个支付宝App为例子，设置好代理。启动app后我们看到捕获的数据请求。如下：


<div>
    <img style="width: 100%;" src="http://gtms04.alicdn.com/tps/i4/TB1IXuBFVXXXXXeXpXX8b0M6VXX-2126-1386.png" alt="Charles 拦截请求">
</div>

我们点击其中的一下请求，查看请求的详细情况，会发现导出是乱码。
这是因为支付宝使用SSL来加密应用和服务器之间的通信。要想看到其中的信息，你就需要欺骗你的手机，设置方面很简单，只需要2个步骤。

###步骤1： 在你的iOS设备上安装Charles 的SSL证书

如果您使用的是iOS4或以上设备，请在您的手机浏览器中访问[http://charlesproxy.com/charles.crt](http://charlesproxy.com/charles.crt)，这是会启动Charles的证书安装过程。

<div>
    <img style="width: 100%;" src="http://gtms03.alicdn.com/tps/i3/TB1ODquFVXXXXa0XFXXOsBu0VXX-640-679.png" alt="Charles 安装SSL证书">
</div>

如果想要在iOS的旧版本或其他模拟器，请查看[Charles官方文档](http://www.charlesproxy.com/documentation/faqs/ssl-connections-from-within-iphone-applications/)


###步骤2：在Charles中配置你需要的SSL代理的域

在Charles中选择 Proxy菜单-> Proxy Settings ，然后选择SSL选项卡。

<div>
    <img style="width: 100%;" src="http://gtms03.alicdn.com/tps/i3/TB1QcyyFVXXXXa.XpXXib55YpXX-2124-1380.png" alt="Charles 安装SSL证书">
</div>

现在，您可以根据您的要求添加多个域，可以使用通配符。

1.*.alipay.com

2.*.google.com

## 再次看Charles 请求

<div>
    <img style="width: 100%;" src="http://gtms02.alicdn.com/tps/i2/TB1HdXUFVXXXXchaXXXqPLHOVXX-2122-1054.png" alt="Charles 安装SSL证书">
</div>

这时我们就能看到https的发出的请求数据。

Charles还有其他有趣功能等待大家挖掘...