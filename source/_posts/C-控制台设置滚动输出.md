---
title: C++控制台设置滚动输出
date: 2020-05-19 22:00:12
excerpt: 如题
tags: C++
categories: Program
---

## 前言
在写C++控制台程序时，我们可能会给程序添加进度条，也就是要程序在同一行反复输出，可以用特殊字符实现。

## 例子

### 在Windows下
```c++
for (int i = 0; i != 10; ++i)
{
    sleep(5); // do something

    printf("\r");
    fflush(stdout);
    printf("i = %d", i);
}
```
### 在Linux下
```c++
for (int i = 0; i != 10; ++i)
{
    sleep(5); // do something

    printf("\r\033[k");
    fflush(stdout);
    printf("i = %d", i);
}
```

## 总结
在这里写一个函数`setScrollOutput()`来实现这一过程：
```c++
inline void setScrollOutput()
{
#ifdef _WIN32
	printf("\r");
#else
	printf("\r\033[k");
#endif // _WIN32
	fflush(stdout);
}
```
使用过程如下：
```c++
for (int i = 0; i != 10; ++i)
{
    sleep(5); // do something

    setScrollOutput();
    printf("i = %d", i);
}
```
