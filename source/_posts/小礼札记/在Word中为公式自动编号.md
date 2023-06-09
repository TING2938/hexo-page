---
title: 在Word中为公式自动编号
date: 2020-07-04 13:22:28
tags: Word
categories: Office
excerpt: Word公式自动编号
---

1. 插入公式

    在Word 2013及以上版本中按下`Alt + =`后即可插入公式。

2. 为公式自动编号
   
   在公式后面输入`#(1)`后`Enter`即可为公式编号
   
    $a^{2}+b^{2}=c^{2}$ #(1) 

   如果公式较多，可以利用Word中`引用->插入题注`为公式自动更新编号：

   - 输入公式时，所有公式的编号都用一个特定符号来表示，如`NUM`
    
     $a^{2}+b^{2}=c^{2}$ #(NUM) 
    
    
   - 在任意空白位置插入题注

    ![](在Word中为公式自动编号/2023-04-03-21-15-45.png)

   - 打开`替换`面板，将`NUM`替换成上面新建的题注，由于替换面板中无法包含题注格式，这时可以先将上面的题注复制到剪贴板上，然后将替换项表示为`^c`(这表示剪贴板内容)

    ![](在Word中为公式自动编号/2023-04-03-21-16-05.png)
    
   - `Ctrl+A`选中全文，右键`更新域`即可显示为正常的连续编号
