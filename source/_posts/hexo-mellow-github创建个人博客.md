---
title: hexo+mellow+github创建个人博客 #标题
date: 2019-08-11 20:50:22 #创建时间
tags: [github, 3-hexo] #标签(同级)
categories: #分类(分层)
    - 技术学习
    - 博客搭建
reward: true#是否开启打赏功能
comment: true#是否开启评论功能
top: 1 #置顶层级(数字越大，优先级越高)
repo: hwolf1 | Daily #用户名 | 仓库名
src: //i.loli.net/2017/12/12/5a2fd18a74471.jpg #主页摘要缩略图(外链以及相对资源均可)
---

#### 一、安装hexo	

​	留下[官方教程](https://hexo.io/zh-cn/docs/)，新建hexo文件夹，安装[Node.js](https://nodejs.org/zh-cn/)和[Git](https://git-scm.com/downloads)，安装成功后，右键该文件夹Git Bash Here，打开命令窗口，下载hexo安装包:

```bash
install hexo-cli -g
```

初始化hexo

```bash
hexo init
```

安装deployer插件

```bash
npm install hexo-deployer-git --save
```

配置hexo根目录下的_config.yml-->>repo: 

```bash
git@github.com:hwolf1/hwolf1.github.io.git
```

设置好github仓库地址，接下来设置SSH KEY:

```bash
git config --global user.email "your@example.com"
git config --global user.name "your_user_name"
ssh-keygen -t rsa -C "你的邮箱" #需要密码的话这里可以设置，以后每次push都需要输入密码，也可以回车忽略
```

将生成的rsa.pub文件内容复制到github上的setting-rsa。同时source文件夹下新建CNAME文件，记事本打开写入：

```bash
huangwei666.com
```



#### 二、安装mellow主题

​	安装需确认你的 Hexo 版本在 3.0 以上，以及 Node 版本为 6.x 以上，在 Hexo 根目录，执行以下命令。

```bash
git clone git@github.com:codefine/hexo-theme-mellow.git themes/mellow
```

将hexo/_config.yml中的更改如下字段：

```bash
theme: mellow
```

安装mellow必备的依赖项：

- hexo-generator-search - local search搜索
- hexo-generator-topindex - 文章置顶
- hexo-helper-qrcode - 二维码分享
- hexo-renderer-less - less解析器

```bash
npm install --save hexo-generator-search@2.1.1 hexo-generator-topindex@0.3.0 hexo-helper-qrcode@1.0.2 hexo-renderer-less@0.2.0
```

设置好后，根据hexo/theme/mellow/下的_config.yml中文注释自行配置主题

更新：已经更换主题为[3-hexo](https://github.com/yelog/hexo-theme-3-hexo)，三栏式，我更喜欢。



#### 三、文本编辑

​	文本编辑采用[Typora](https://www.typora.io/#windows)软件进行编辑，对于图片编辑，参考[博客](https://blog.csdn.net/xjm850552586/article/details/84101345)，首先把主页配置文件_config.yml 里的这个选项设置为

```xml
post_asset_folder:true
```

其次hexo目录下执行这样一句话

```bash
npm install hexo-asset-image --save
```

这是下载安装上传本地图片的插件，使用如下：

```bash
hexo n 文件
```

生成文件.md并且在source/ _posts生成对应的文件夹，将图片放到对应的文件夹，在md文件中插入

```markdown
{% asset_img 图片名.jpg This is an example image %}
```



#### 四、发布博客

​	在Typora编辑好文档后，在bash中执行：

```
hexo clean   --->    hexo d -g
```

当然也可以将上诉命令保存在~/.bashrc中，下次直接调用hd、hs即可

```bash
alias hs='hexo clean && hexo g && hexo s'  #启动本地服务
alias hd='hexo clean && hexo g && hexo d'  #部署博客
```

编译并且上传代码，将图片放到对应的文件夹，直接调用。示例博客内容如下：

{% asset_img 博客示例.jpg %} 

第一次就到这里吧！下次见！拜了个拜！



```c
				/*
				* Company : 
				* @author : 
				* @date   :  
				* @version: 1.0
				* 
				* .....................我佛慈悲........................
				*                       _oo0oo_
				*                      o8888888o
				*                      88" . "88
				*                      (| -_- |)
				*                      0\  =  /0
				*                    ___/`---'\___
				*                  .' \\|     |// '.
				*                 / \\|||  :  |||// \
				*                / _||||| -卍-|||||- \
				*               |   | \\\  -  /// |   |
				*               | \_|  ''\---/''  |_/ |
				*               \  .-\__  '-'  ___/-. /
				*             ___'. .'  /--.--\  `. .'___
				*          ."" '<  `.___\_<|>_/___.' >' "".
				*         | | :  `- \`.;`\ _ /`;.`/ - ` : | |
				*         \  \ `_.   \_ __\ /__ _/   .-` /  /
				*     =====`-.____`.___ \_____/___.-`___.-'=====
				*                       `=---='
				* -卍-卍-卍-卍-卍-卍-卍-卍-卍-卍-卍-卍-卍-卍-卍-卍-卍-
				*
				*..................佛祖开光 ,永无BUG................... 
				*/

```

