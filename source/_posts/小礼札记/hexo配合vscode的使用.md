---
title: hexo配合vscode的使用
date: 2023-04-03 21:25:46
categories: 教程
tags: hexo
excerpt: hexo使用
---

## 解决插入图片问题

我们要实现在本地写markdown时，方便插入图片，能在vscode中正确预览，hexo发布后也能正确显示，可以安装一下步骤进行：

1. 安装截图工具`Snipaste`

   微软应用商店搜索下载即可

   截图时可以选择将图片复制到剪贴板，并通过下面的插件将图片放到markdown中

2. 安装vscode插图插件
   
   有两个插件，任选其一即可
   
   1. `Paste Image`，并作如下配置
   
        ```json
        // .vscode/settings.json
        {
            "pasteImage.path": "${currentFileDir}/${currentFileNameWithoutExt}",
        }
        ```

    2. `Hexo Utils`插件，
   
    这两个插件都可以将剪贴板中的图片插入到markdown中，插图快捷键为`Ctrl`+`Alt`+`V`


3. 安装`hexo-asset-image`

    这个插件能识别插入图片的路径，并在执行`hexo g`时生成正确的链接

    ```
    npm install https://github.com/CodeFalling/hexo-asset-image --save
    ```

    同时还要更改`_config.yml`

    ```
    post_asset_folder: true
    ```

    