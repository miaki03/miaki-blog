+++
date = '2026-07-10T05:56:51+08:00'
draft = false
title = '静态页面博客搭建的尝试'
description = "主要记录环境选择和搭建"
categories = ["技术分享"]
image = "/imge/a5.jpg"
+++
## 项目介绍  
**Hugo是什么？** Hugo 是一款用 Go 编写的静态网站生成器，优化速度并设计灵活。凭借先进的模板系统和快速的资产流水线，Hugo能够在几秒钟内渲染完整网站，通常更短。通俗一点的说法是，使用者只需通过文章和配置文件便可构建网站，实现许多功能，而无需处理繁琐的前端页面。  

  
## 环境准备  
**Windows11 + wsl2 上的[ubuntu24.04](https://baike.baidu.com/item/Ubuntu/155795)**  
WSL是在Windows上的Linux子系统，可以为我们提供轻量便捷的本地调试环境，使开发与调试无需从安装系统开始，即使遇到令人困惑环境问题也可以低成本重置环境。
### [安装wsl2](https://learn.microsoft.com/zh-cn/windows/wsl/install)
打开powershell并以管理员身份运行，键入以下命令开始安装wsl  
```powershell
wsl --install -d ubuntu-24.04
```  
**注意：首次安装需要重启，请确保已保存其他文件**  
重启过后，再次打开powershell，键入命令查看已安装的环境  
```
wsl -l -v
```  
如果为以下输出即没有问题：  
```
  NAME                      STATE            VERSION
  ubuntu-24.04          Running         2
```
然后进入环境  
```powershell
wsl -d ubuntu-24.04
```  
**注意：首次进入需要设置用户名和密码，请牢记您的密码**  
如下格式代表您已进入wsl的Linux命令行界面：  
```
用户名@主机名:/mnt/c/Users/用户名$
```
*WSL安装完成*  
### [安装Hugo](https://hugo.opendocs.io/)

接下来，直接键入``cd``即可直接回到home目录  
使用wget命令，通过链接直接下载hugo-extend版文件，[Stack主题](https://github.com/CaiJimmy/hugo-theme-stack)的许多功能需要extend版本才可实现。（ **注意：附带的链接是x86架构的版本，如果是arm架构的电脑需要更换[下载链接](https://github.com/gohugoio/hugo/releases/)！** ）  
```
wget https://github.com/gohugoio/hugo/releases/download/v0.164.0/hugo_extended_0.164.0_linux-amd64.deb
```  
使用``ls``查看当前目录，确认文件下载成功  
使用``dpkg -i 文件名.deb``安装Hugo（可以使用Tab键补全文件名）  
安装完毕后，使用``hugo version``查看版本，如果类似以下输出即安装成功：
```
hugo v0.164.0-ce2470e7012b5ab5fc4e10ebe4027e9f8d9e00dc+extended linux/amd64 BuildDate=2026-07-06T16:39:30Z VendorInfo=gohugoio
```
*Hugo安装完成*  
### 安装Git  
依次执行以下命令安装Git，我们需要使用Git管理主题和托管博客  
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
这个命令会创建我们工作区的目录结构，我们的配置文件、文章和主题等内容，会分别存储在不同的文件夹里  
进入该文件夹（``cd 目录名``）  
使用``git init``初始化当前目录为仓库  
打开[Stack主题](https://github.com/CaiJimmy/hugo-theme-stack)页面，将主题fork到自己的仓库，这样便于我们之后修改主题，比如修改默认图标库等  
接下来将主题作为子仓库添加到theme目录下：  
```
git submodule add 你的主题仓库clone链接（例：https://github.com/你的用户名/hugo-theme-stack.git） themes/hugo-theme-stack
```
然后就可以查询官方文档完善配置即可，若追求开箱即用可以直接复制主题文件中的模板。  
我难以维持一开始这样过于严谨和完美的文风，导致最复杂的配置阶段迟迟不能完笔。  
所以在此收尾，等到日后博客更新或者迁移时再度完善。