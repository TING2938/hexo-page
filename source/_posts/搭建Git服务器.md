---
title: 搭建Git服务器
date: 2020-11-12 08:44:50
tags: Linux
categories: Linux
excerpt: 搭建Git服务器
---

## 缘起

[Git](https://git-scm.com/)是一种版本控制的开源软件，由Linux之父Linus开发的。它是一种分布式版本控制系统，不需要服务器软件就可以进行版本控制，这使得源代码的发布以及多人协作时交流十分便捷，Git软件普遍预装在Linux各个发行版中，查看系统中的Git版本号：

```bash
$ git --version
git version 1.7.1
```

## 搭建远程Git服务器

搭建远程Git服务器的要求很低，只需要本地机器能通过ssh访问远程服务器

创建过程特别简单，首先在**远程服务器**中：

```bash
$ mkdir -p ~/gitServer # 创建一个目录来作为代码仓库
$ cd ~/gitServer
$ git init # 创建一个空的git仓库
$ git config receive.denyCurrentBranch ignore
```

至此远程Git服务器搭建**完成**

## 在本地机器上进行源代码管理

- 首先，在本地`clone`远程仓库：

  ```bash
  $ mkdir user1
  $ cd user1
  $ git clone ssh://<user>@<ip>:<port>/path/to/.git  # clone远程仓库到本地
  $ cd gitServer
  $ ls -a # 会有一个.git的隐藏文件夹
  .  ..  .git 
  ```

- 推送本地代码到远程服务器
  
  ```bash
  $ touch readme.md # 创建一个文件
  $ git add . # 添加要推送的文件
  $ git commit -m "First push" # 添加推送信息
  $ git push # 推送文件到远程服务器
  ```

- 远程服务器上看更新的文件
  
  ```bash
  $ git reset --hard
  ```
