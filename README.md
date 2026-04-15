[English README](./docs/README_EN.md) /[Telegram](https://t.me/yume_yuki)/[QQ](https://qm.qq.com/q/dCn4enLQly)

# LINE贴图包和emoji下载器

这个项目可以用来下载LINE上的贴纸和emoji，同时支持动图和静态图，以及批量下载的操作。所有python脚本内容的生成均来自于AI（chatGPT-4o, Gemini1.5PRO）
本项目禁止用于非法用途，禁止贩卖。**如果喜欢这些stickers，请支持正版line贴纸**

## 目录

- [LINE贴图包和emoji下载器](#line贴图包和emoji下载器)
  - [目录](#目录)
  - [脚本依赖](#脚本依赖)
  - [使用方法](#使用方法)
  - [报错与解决](#报错与解决)
    - [1. 无法获取表情包名](#1-无法获取表情包名)
    - [2. 无法下载](#2-无法下载)
    - [3. 下载后未删除temp文件](#3-下载后未删除temp文件)
    - [4. 下载不完全](#4-下载不完全)
    - [5. 其他](#5-其他)
  - [鸣谢](#鸣谢)
  - [许可证](#许可证)

## 脚本依赖

> 首先请确保你的电脑里安装了**python3.11**以上的版本且将python列入计算机中的**PATH**！确保你的pip是最新版本，你可以通过运行`python -m pip install --upgrade pip`来更新你的pip。

运行下面的命令以安装依赖库：

```bash
pip install -r requirements.txt
```

## 使用方法

| 文件名       | 功能                                                                 | 使用方法                                                                                                                                                                                                                                                                                                                                                                   |
|--------------|----------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `main.py`    | 三种模式：<br>1. 下载单个表情包<br>2. 下载作者的所有表情包<br>3. 读取 txt 文件批量下载 | 在终端中运行 `python main.py`，根据提示选择模式：<br> • **模式1**：输入 `1` 后，选择是否下载到指定文件夹（输入 `y` 并指定路径，或输入 `n` 下载到当前目录），然后粘贴单个表情包或贴图的商品链接，程序将下载并自动清理包内 `key` 文件。<br> • **模式2**：输入 `2` 后，同样先选择下载文件夹，然后粘贴作者主页链接（例如 `https://store.line.me/author/xxx`），程序会自动遍历所有分页，下载该作者的全部表情包。<br> • **模式3**：输入 `3` 后，先选择下载文件夹，然后输入 txt 文件的路径（直接回车使用当前目录下的 `bdp.txt`）。txt 文件中每行一个链接（可以是商品链接或作者链接），程序将批量处理。 |

- 支持的表情包类型：LINE 普通贴图（`/stickershop/product/`）和表情符号（`/emojishop/product/`）。
- 所有下载的 zip 包会以表情包名命名，并自动删除内部的 `key` 文件。
- 若选择下载到指定文件夹，路径不存在时会自动创建。

## 报错与解决

### 1. 无法获取表情包名

如果下载后的文件名为`unknown_emoji_name`，请检查您的网络环境，您的网络ip是否在line提供服务的区域外。

### 2. 无法下载

如果程序运行后报错并在目录下留下了一个空文件夹，请提起issues并尝试复现内容。问题曾经出现过，但是问题解决后忘记了如何复现问题。

### 3. 下载后未删除temp文件

- 如果你用的手机termux并在storage目录尝试下载，那你真是buff叠满了，部分手机的termux在storage目录及其子目录下删除文件会被系统拦截。
- 如果你用的是别的设备或未在storage目录下出现此错误，请检查你是否有该文件夹目录下的权限。

### 4. 下载不完全

- 当创作者的表情包上传数量超过了36个时，表情包仅能嗅探单页的表情包，请使用`bdp.py`下载，将作者的所有表情包页面url粘贴进`bdp.txt`。
- `v0.2.4`版本后已修复此问题。

### 5. 其他

如果你遇到了除以上问题外的其他问题，请提起issues并列出详细复现问题过程记录并提交。感谢你对本项目的支持。

## 鸣谢

感谢以下朋友及contributor：(排名不分先后)
[@CPuddingOwO](https://github.com/CPuddingOwO) | [@kaixinol](https://github.com/kaixinol) | [@ZGQ Inc.](https://github.com/ZGQ-inc)

## 许可证

```
MIT License

Copyright (c) 2024 元亓

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```
