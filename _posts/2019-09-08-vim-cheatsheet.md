---
layout: post
title: Vim Cheatsheet
categories: Linux
description: vim 简明入门教程
keywords: Vim, Linux
---



> * Vim 是vi 发展起来的文本编辑器，其强大不用再强调，这里只介绍一些基本的入门技巧
>
> * 连 vim 的官方网站 ([http://www.vim.org](http://www.vim.org/)) 自己也说 vim 是一个程序开发工具而不是文字处理软件
>
> * 参考: https://www.runoob.com/linux/linux-vim.html

# 模式

基本上 vi/vim 共分为三种模式，分别是

* **命令模式（Command mode）**
* **输入模式（Insert mode）**
* **底线命令模式（Last line mode）**

## 命令模式

**用户刚刚启动 vi/vim，便进入了命令模式**。

此状态下敲击键盘动作会被Vim识别为命令，而非输入字符。比如我们此时按下i，并不会输入一个字符，i被当作了一个命令。

以下是常用的几个命令：

- **i** 切换到输入模式，以输入字符。
- **:** 切换到底线命令模式，以在最底一行输入命令。

**重点：命令模式只有一些最基本的命令，因此仍要依靠底线命令模式输入更多命令。**

## 输入模式

在命令模式下按下i就进入了输入模式。

在输入模式中，可以使用以下按键：

- **字符按键以及Shift组合**，输入字符
- **ENTER**，回车键，换行
- **BACK SPACE**，退格键，删除光标前一个字符
- **DEL**，删除键，删除光标后一个字符
- **方向键**，在文本中移动光标
- **HOME**/**END**，移动光标到行首/行尾
- **Page Up**/**Page Down**，上/下翻页
- **Insert**，切换光标为输入/替换模式，光标将变成竖线/下划线
- **ESC**，退出输入模式，切换到命令模式

## 底线命令模式

**在命令模式下按下:（英文冒号）就进入了底线命令模式。**

**底线命令模式可以输入单个或多个字符的命令，可用的命令非常多。**

在底线命令模式中，基本的命令有（已经省略了冒号）：

- q 退出程序
- w 保存文件

**按ESC键可随时退出底线命令模式。**

简单的说，我们可以将这三个模式想成底下的图标来表示：

![img](/images/wiki/breaststroke.png)

![img](images/wiki/breaststroke.png)

![img](assets/vim-vi-workmodel.png)



# 常用操作

> 这里只介绍常用的操作



# 速记键盘图

![img](assets/vi-vim-cheat-sheet-sch.gif)
