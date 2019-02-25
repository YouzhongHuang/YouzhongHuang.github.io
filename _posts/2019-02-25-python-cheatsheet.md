---
layout: post
title: Python Cheatsheet
categories: Python
description: 一份简明的 Jupyter Python 笔记与教程
keywords: Python, Jupyter, PDB
---

[TOC]

> Jupyter是非常优秀的Python开发环境，融合了Python IDE和Markdown

# Jupyer 使用

## 两种模式

> 类似vi
* 命令模式：`Esc`键进入
* 编辑模式：`Enter`键进入

## 两种Tab
> 不懂就Tab
* `Tab` 自动补全，列出类成员
* `Shift-Tab` **tooltip**，详细信息，有惊喜 `👍`

## 三种Enter
* `Enter` 换行`@编辑模式`，或进入编辑模式`@命令模式`
* `Ctrl-Enter` 运行cell `👍`
* `Shift-Enter` 运行cell，并跳到下一cell

## 列出所有
```python
dir()
```
## 执行shell命令
```python
!command
```
> 这点与MATLAB一样
> command是操作系统的命令，Windows和Unix是不一样的，如，在Windows下`!ls`会出错

## 删除cell
`Esc d d` 进入命令模式后，按两次d

## 注释
* `Ctrl-/`

# PDB调试

## 经典方法一

- 不需要修改源代码，直接开始调试
- 缺点是从入口处开始调试
- 运行方式

```bash
>> python -m pdb test.py
```

## 经典方法二

```python
import pdb
...
pdb.run('command')
...
```

```python
import pdb
...
pdb.set_trace()
...
```

将在pdb中调试command

参考：https://docs.python.org/3.5/library/pdb.html#debugger-commands

## Jupyter魔法方法

- 在cell的首行添加`%%debug`
- 运行该cell，即可进入调试模式`👍`

# Jupyter Magic

> **`约定`**：`%%`开头的命令作用于整个ceil，`%`开头的作用于当前行
## List all magic
```python
%lsmagic
```
## Current directory
```python
%pwd
```
## List all variables
```python
%who 
%whos #与MATLAB一致
```
## Timing
*   `%prun`执行一次，统计所有模块的耗时，类似MATLAB的方式
```python
import numpy
%prun numpy.random.normal(size=100) 
```
*   `%time`将会执行1次，给出时间
```python
import numpy
%time numpy.random.normal(size=100) 
```
*   `%timeit`将会执行100000次(默认情况下)，然后给出时间统计
```python
import numpy
%timeit numpy.random.normal(size=100) 
```
*   `%%time`将会给出cell的代码运行一次所花费的时间。
```python
%%time
import numpy
for _ in range(100000):
    numpy.random.normal(size=100) 
```
## Export /Show script
* `%%writefile`保存cell的内容到一个外部文件
```python
%%writefile test.py
import numpy
for _ in range(100000):
    numpy.random.normal(size=100) 
```
* `%pycat`则刚好相反，并且会向你展示高亮后的外部文件
```python
%pycat test.py
```

## Excute code

```python
%run ./test.py #在cell中执行test.py
```
> `%run` 并不等于`import`

## Insert code
```python
%load ./test.py #使用test.py来代替cell内容
```
## Plotting in notebooks
在notebook中生成绘图有许多选项：
*   matplotlib， 使用`%matplotlib inline`进行激活。
*   `%matplotlib notebook`提供了一些交互性，不过可能会有点慢，因为渲染由服务器端完成。

# Jupyer 扩展插件
```bash
pip install jupyter_contrib_nbextensions && jupyter contrib nbextension install 
```
然后启动Jupyter Notebook并导航到新的Nbextensions拓展选项卡，勾选：
`Variable inspector` 类似于MATLAB的变量查看器
`Table of Contents` 跳转目录
`ExecuteTime`  自动统计每次执行的时间
`Autopep8` 代码格式化


> 参考：
> https://www.cheatography.com/weidadeyue/cheat-sheets/jupyter-notebook/pdf_bw/
> https://www.jianshu.com/p/dacc6acba00b

