+++
date = '2026-07-10T05:56:51+08:00'
draft = false
title = '如何搭建一个静态页面博客'
description = "这篇文章还不该出现在这里QAQ"
categories = ["技术分享"]
image = "/imge/a5.jpg"
+++
## 项目介绍  
**Hugo是什么？** Hugo 是一款用 Go 编写的静态网站生成器，优化速度并设计灵活。凭借先进的模板系统和快速的资产流水线，Hugo能够在几秒钟内渲染完整网站，通常更短。  

  
## 环境准备  
**Window11 + wsl2 上的[ubuntu24.04](https://baike.baidu.com/item/Ubuntu/155795)**  
wsl会为我们提供轻量便捷的本地调试环境。
### [安装wsl2](https://learn.microsoft.com/zh-cn/windows/wsl/install)
打开powershell并以管理员身份运行，键入以下命令开始安装wsl  
```
wsl --install
```  
**注意：首次安装需要重启，请确保已保存其他文件**  
重启过后，再次打开powershell，键入命令查看已安装的环境  
```
wsl -l -v
```  
如果为以下输出即没有问题：  
```
  NAME            STATE           VERSION
  Ubuntu          Running         2
```
然后进入环境  
```
wsl -d ubuntu
```  
**注意：首次进入需要设置用户名和密码，请牢记您的密码**  
如下格式代表您已进入wsl的Linux命令行界面：  
```
用户名@主机名:/mnt/c/Users/用户名$
```
*WSL安装完成*  
### [安装Hugo](https://hugo.opendocs.io/)

接下来我们回到home目录，直接键入``cd``即可  
键入以下命令下载hugo的发行版文件：  
```
wget https://github.com/gohugoio/hugo/releases/download/v0.164.0/hugo_extended_0.164.0_linux-amd64.deb
```  
使用``ls``查看当前目录，可以看到文件已下载  
使用``dpkg -i 文件名.deb -y``安装Hugo（可以使用tab补全）  
安装完毕后，使用``hugo version``查看版本，如果类似以下输出即安装成功：
```
hugo v0.164.0-ce2470e7012b5ab5fc4e10ebe4027e9f8d9e00dc+extended linux/amd64 BuildDate=2026-07-06T16:39:30Z VendorInfo=gohugoio
```
*Hugo安装完成*  
### [安装Git]()  
依次执行以下命令安装git  
```
sudo apt update
sudo apt install git -y
```
安装完毕后使用``git -v``确认安装是否成功，类似输出：  
```
git version 2.43.0
```
*Git安装完毕*  
## [开始部署](https://hugo.opendocs.io/getting-started/quick-start/)
运行以下命令开始搭建你的博客：  
```
hugo new site 博客项目文件夹名称
```
这个命令会创建我们工作区的目录结构，进入该文件夹（``cd 目录名``）  
使用``git init``初始化当前目录为仓库，我们将使用git管理我们的主题和文章  
打开[Stack主题](https://github.com/CaiJimmy/hugo-theme-stack)页面，将主题fork到自己的仓库，这样便于我们之后修改主题  

___

