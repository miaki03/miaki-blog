+++
date = '2026-10-22T20:23:16+08:00'
draft = false
title = 'TUST开源学习笔记01'
description = "第一次课堂的笔记"
categories = ["技术分享"]
image = "/img/cover.jpg"
+++

## git使用的基本流程

首先，将当前目录初始化为一个git仓库

git init

然后，将当前目录下所有文件添加到暂存区

git add . #"."代表当前目录下所有文件

将暂存区文件提交为一次commit，并且认真写massage

git commit -m "first commit"

最后，将修改推送到仓库

git push

## 我的电脑的环境

因为没有使用cdn.cool，所以我需要手动把我的工作区和远程仓库用git连接

首先生成一对ssh密钥

ssh-keygen -t ed25519 -C "邮箱地址"

然后，找到公钥，并填写到远程仓库对应位置，勾选读写权限

cat ~/.ssh/id_ed25519.pub

(可选，使用‘ssh -T git@github.com’进行连接测试)

然后将本地仓库和远程仓库关联

git remote add origin 远程仓库的ssh地址

首次推送，并且建立追踪关系

git push -u origin main

之后就可正常使用和推送了

## 我遇到的问题

在我执行‘git push -u origin main’时，遇到了如下错误：

remote: error: GH007: Your push would publish a private email address.

原因是我曾经在这个环境配置过git的全局用户和邮箱地址，但是我之后某次将github改成了隐私邮箱保护，使用真实邮箱触发了安全策略所以推送失败

所以需要修改邮箱配置（踩雷了，全局邮箱还是没变，我那个时候改动的时当前工作区的git邮箱记录，之后别的仓库还会遇到同样的问题，还得重新修改）

#修改当前仓库的邮箱配置
git config user.email "你的ID+你的用户名@users.noreply.github.com"

之后重置提交信息

git commit --amend --reset-author --no-edit

最后重新提交即可

## 额外笔记

使用gcc编译程序

gcc c程序名.c -o 执行程序名

编译过程：

gcc -E hello.c -o hello.i #预处理
gcc -S hello.i -o hello.S #汇编
gcc -c hello.S -o hello.o #中间语言
gcc hello.o -o hello #机器码