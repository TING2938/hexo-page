---
title: Linux常用命令（持续更新中...）
date: 2020-11-17 20:37:42
tags: Linux
categories: Linux
excerpt: linux中的常用命令
---

## `find`

- `find . -type f -size +1G`
  - 查找大于1G的所有文件（或+10M，为大于10M的文件）

## `grep`

- `grep -v cpp$`
  - `-v` 代表反向选取，即选择不以`cpp`结尾的行 
  - `egrep -v "trr|edr|xvg|[0-9]$"` 反向选取多个字段，采用`egrep`(即正则表达式的版本)
- `echo "Modify: 2020-11-24 11:09:22.584500109 +0800" | grep -oP "\d{4}-\d{2}-\d{2}"`
  - 输出：2020-11-24
  - `-o`代表只输出匹配的部分

## `du`

`du`统计文件以及文件夹大小

- `du -sh`
  - 统计当前文件占用大小
- `du -d 1 -h`
  - `-d 1` 代表统计文件夹深度为1
