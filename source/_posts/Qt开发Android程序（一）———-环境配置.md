---
title: Qt开发Android程序（一）——— 环境配置
date: 2020-06-17 12:08:57
tags:
  - Qt
  - C++
categories: Program
excerpt: Qt for Android环境配置
---

## 开发环境

Qt Creator(QC)作为IDE，在安装QC时需要选择安装Android模块，此外，还需安装NDK，JDK，SDK开发套件。

- NDK

    下载[android-ndk-r21-windows-x86_64.zip](https://developer.android.com/ndk/downloads/index.html)后安装

- JDK

    下载[jdk-8u5](http://jdk.android-studio.org)后安装

- SDK
  
    到[此处](http://sdk.android-studio.org)下载最新版SDK，SDK安装好后，打开SDK Manager，安装如下图所示项目：

    ![](/images/SDK1.png)

    这里选择Android 7.1.1(API 25)套件

    ![](/images/SDK2.png)

    ![](/images/SDK3.png)

- 配置Qt Creator
  
  打开菜单栏工具-选项-设备，将SDK，JDK，NDK路径填入

  ![](/images/QC1.png)

- 配置虚拟机(AVD)
  
  打开AVD manager，点击右侧Creat创建一个虚拟机，参数配置如下（如果自己手机方便的话也可以直接用手机调试）：

  ![](/images/AVD1.png)

  点击Start查看运行效果

  ![](/images/AVD2.png)

## 简单的例子

1. 打开Qt Creator，新建一个QWidget项目，创建一个按钮

    ```c++
    #include "mainwindow.h"
    #include <QVBoxLayout>
    #include <QHBoxLayout>
    #include <QPushButton>

    MainWindow::MainWindow(QWidget *parent)
        : QWidget(parent)
    {
        this->setupUI();
    }

    void MainWindow::setupUI()
    {
        auto vbox = new QVBoxLayout();
        this->setLayout(vbox);

        auto btn =new QPushButton("Click here");
        auto hbox = new QHBoxLayout();
        hbox->addStretch(1);
        hbox->addWidget(btn);
        hbox->addStretch(1);

        vbox->addLayout(hbox);

        connect(btn, &QPushButton::clicked, [=](){
            btn->setText("Changed");
        });
    }
    ```
2. 点击QC左侧项目，配置Android项目
   
   在Build步骤里，ABIs选择**x86_64**，Android build SDK选择**android-25**

   ![](/images/QC2.png)

   ![](/images/QC3.png)

3. 调试
   
   点击左下角锤子符号编译，点击绿色三角运行，选择前面配置的虚拟机作为调试机，查看运行效果

   ![](/images/AVD3.png)