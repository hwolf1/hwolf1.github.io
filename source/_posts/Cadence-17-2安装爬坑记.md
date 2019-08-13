---
title: Cadence_17.2安装爬坑记
date: 2019-08-11 22:48:17
tags: [cadence, 安装] #标签(同级)
categories: #分类(分层)
    - 技术学习
    - cadence
reward: true#是否开启打赏功能
comment: true#是否开启评论功能
top: 1 #置顶层级(数字越大，优先级越高)
repo: hwolf1 | Daily #用户名 | 仓库名
src: //i.loli.net/2017/12/12/5a2fd18a74471.jpg #主页摘要缩略图(外链以及相对资源均可)
---

#### 一、下载安装包

这里还是推荐[老吴的包](https://www.mr-wu.cn/cadence-orcad-allegro-resource-downloads/)，也可以到[EDA365](http://www.eda365.com/thread-187152-1-1.html)下载。这里主要下载cadence SPB17.2和Hotfix_SPB17.2最新补丁。

{% asset_img 安装文件.jpg %} 

#### 二、安装pojie

安装主要采用流行的[阿里狗](http://aligou.mr-wu.cn/)，但是经过我的实验，不要使用阿里狗来进行安装，采用阿里狗一条龙安装好的话会出现打完补丁，所有的快捷方式无效的问题，其他问题暂时没有发现。手动安装的话就是：

- 先安装SPB主程序和License Manager
- 再安装Hotfix_SPB17.2的最新补丁（自动安装到同一个文件夹）
- 最后打开阿里狗进行pojie

{% asset_img 破解.jpg %} 

#### 三、软件说明

cadence这个软件说它是个KFC全家桶不过分吧，对初学者极其不友好（相对于友商AD--->号称“野鸡工具”），你看看它有多少工具

{% asset_img 开始菜单.jpg %} 

我们需要用的主要就是Capture CSI、Padstack Editor（图片有错）、PCB Editor。打开Capture CSI，选择这个：

{% asset_img capture.jpg %} 

看，好不容易打开软件还要选这么多，其他相关的我也不知道有啥区别，打开界面都一样，反正听Dalao的。

PCB Editor打开选择

{% asset_img pcb.jpg %} 

然后你就可以开始愉快的是用软件了。？？？这么多怎么使用？？？习惯了AD一体化的软件界面，发现cadence真的好丑有木有 ，好在有学习教程可以用，这里推荐[小哥的cadence132讲](https://www.moore8.com/courses/2102)，边看边学，找个板子画画，还是能很快上手的。基本开发流程是：

1. 绘制器件的原理图库，并绘制原理图，生成网络表
2. 利用Padstack Editor设计焊盘以及封装
3. PCB Editor导入网络表，设计PCB（好像是这样，还没看到这儿！手动滑稽.jpg  ヽﾐ ´∀｀ﾐノ＜）

嗯！大概就是这样！拜了个拜！

{% asset_img 逗逼.gif %} 