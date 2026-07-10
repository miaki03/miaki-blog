+++
date = '2026-07-10T05:56:51+08:00'
draft = true
title = '基于Hugo+Ngnix的静态个人博客搭建记录'
description = "这篇文章还不该出现在这里QAQ"
categories = ["草稿"]
image = "/imge/a5.jpg"
+++
# 项目介绍  
**Hugo是什么？** Hugo 是一款用 Go 编写的静态网站生成器，优化速度并设计灵活。凭借先进的模板系统和快速的资产流水线，Hugo能够在几秒钟内渲染完整网站，通常更短。  
**Nginx是什么？** Nginx 是一个高性能的 HTTP 服务器和反向代理服务器。不过在这个项目我们只需要用到 HTTP 服务就行。  
  
# 环境准备  
**Window11 24h2 + wsl2 上的[ubuntu24.04](https://baike.baidu.com/item/Ubuntu/155795)**  
选择在wsl2上部署，是因为环境接近云服务器的linux环境，更贴近真实的网站部署。  
## [安装wsl2](https://learn.microsoft.com/zh-cn/windows/wsl/install)
首先打开 Powershell 并且以管理员身份运行  
图片  
然后键入下列命令查看支持的 Linux 发行版  
`wsl --list --online`  
我们选择的环境是ubuntu24.04，所以键入命令  
`wsl --install -d ubuntu24.04`

___

🚧*施工中……*