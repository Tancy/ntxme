---
layout: post
title:  "Designing Fluid Interfaces"
description: 探索iOS和Apple其他平台顺滑和动态界面的技术。 了解如何设计手势和动画，直观感觉，自然，使您的应用令人愉快的使用。
cover_image: images/803_designing_fluid_interfaces.jpg
categories:
  - Blog
tag:
  - Design
  - Apple
date: 2018/06/10 20:57:06
---

Android系统自诞生以来的很多年使用体验上不都如iOS（更不用说相同硬件配置的情况了），其中就一个列表滚动的体验也是最近几年才接近iOS的体验。

这次WWDC2018上，专门有一个议题分享了iOS是怎么做。非常值得观看。

[视频地址](https://developer.apple.com/videos/play/wwdc2018/803/)

[PDF](https://devstreaming-cdn.apple.com/videos/wwdc/2018/803lpnlacvg2jsndx/803/803_designing_fluid_interfaces.pdf?dl=1)

本文简单的概述为何你的iOS的用户界面用起来这么顺滑。 

## 手势操作的预判与反悔

在手势操作中, 并不是像普通的点击操作, 完成一个操作以后再进行一个. 
如果是完成一个手势, 才能进行下一个的话, 就会出现卡的感觉. 

在iOS里面的设计是, 对手势操作全都有预判, 并且对下一步操作有提前量.
同时, 当你在手势操作过程中, 可以反悔. 当你不想启动程序的时候, 可以理解启动另一个手势. 
如下就是实例. 


##### 返回主界面的时候可以滑动主界面

![](/images/designing_fluid_interfaces/Swipe_homescreen_pages_while_going_home.gif)
<br/>
<br/>

##### 在程序运行的时候启动多任务切换

![](/images/designing_fluid_interfaces/Go to multitasking while app is launching.gif)
<br/>
<br/>
##### 程序运行的时候关闭程序

![](/images/designing_fluid_interfaces/Close app while launching app.gif)
<br/>
<br/>

##### 程序启动中就可以开始操作
![](/images/designing_fluid_interfaces/Interact with app as it launches.gif)

<br/>
<br/>

## 计算位置动量 速度 力量


如何激发多任务手势, 不是按照你滑动手指的时间来判断的, 按照你滑动的速度力量, 动量距离来判断什么时候激发多任务窗口. 
![](/images/designing_fluid_interfaces/How can we detect this pause in motion?.gif)
<br/>
<br/>



## 动画转化加速度
动画切换速度是有加速度的, 当你觉得窗口或者物体是加速向你靠近. 

![](/images/designing_fluid_interfaces/Hint in the direction of the gesture.gif)
<br/>
<br/>



## 如何管理按击区域

触摸按键的区域, 并不是准确的, 是在按钮的一个区域里面, 比如在计算器里, 当你按一个数字的时候, 你的触摸区域会在数字的圆圈里面, 并且还会在外面一点, 这样当你反悔的会后, 将手指移出区域, 按钮操作就会消失, 而当你返回的时候, 按钮数字会重新被选择. 

![](/images/designing_fluid_interfaces/Responding to Interaction.gif)
<br/>
<br/>



## 3DTouch点按重量判断激发操作

![](/images/designing_fluid_interfaces/Provide continuous feedback.gif)
<br/>
<br/>


![](/images/designing_fluid_interfaces/Go to multitasking while app is launching.gif)

## 3DTouch与滚动切换. 

当用户激发了3D Touch后, 其实是用户按错了, 要是滚动, 那3D Touch操作就被取消, 重新执行滚动操作. 

![](/images/designing_fluid_interfaces/Combining gestures.gif)
<br/>

## Fluidity as a Medium

![](/images/designing_fluid_interfaces/Fluidity as a Medium.gif)
<br/>