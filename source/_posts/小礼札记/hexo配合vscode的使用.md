---
title: hexo配合vscode的使用
date: 2023-04-03 21:25:46
excerpt: hexo使用
tags: hexo
---

## 解决插入图片问题

我们要实现在本地写markdown时，方便插入图片，能在vscode中正确预览，hexo发布后也能正确显示，可以安装一下步骤进行：

1. 安装截图工具`Snipaste`

   微软应用商店搜索下载即可

   截图时可以选择将图片复制到剪贴板，并通过下面的插件将图片放到markdown中

2. 安装vscode插件`Paste Image`，并作如下配置
   
    ```json
    // .vscode/settings.json
    {
        "pasteImage.path": "${currentFileDir}/${currentFileNameWithoutExt}",
    }
    ```
    这个插件可以将剪贴板中的图片插入到markdown中，通过上面的配置，在插入图片时，会在当前文件的路径下生成去除扩展名的文件夹，并将图片放到里面

3. 安装`hexo-asset-image`插件

    这个插件能识别插入图片的路径，并在执行`hexo g`时生成正确的链接

    ```
    npm install https://github.com/CodeFalling/hexo-asset-image --save
    ```

    同时还要更改`_config.yml`

    ```
    post_asset_folder: true
    ```

    