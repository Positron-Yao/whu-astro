---
layout: mypost
title: PAGE - Tkinter开发助手
categories: [Python, Tkinter, GUI]
---

PAGE是一款拖拽式Tkinter IDE，支持拖拽式界面开发及Python代码生成（类比PyQt），极大地提高了Tkinter的开发效率。

## 安装

下载PAGE源码或安装包，并将快捷方式中的 ``PAGE.bat`` 改为 ``PAGE.py`` （原版有一点点问题）。或通过PAGE.py直接运行。

## 使用

![page界面](page界面.png)

打开PAGE后，会看到五个窗口，分别是主菜单、工具栏、主窗口、树状图、属性栏。大多数操作将在工具栏、主窗口、属性栏进行。

## 主窗口

即Toplevel，由PAGE自动创建，在工具栏点击某一工具后可以点击主窗口来放置，拖拽改变位置，键盘上下左右可以微调，双击可以设置输入值等。

## 工具栏

下面大致写一下常用工具的用法及注意事项。

### Button

链接到一个函数，在 ``***_support.py`` 中，具体功能自己更改（默认是一个print）。

记得写一个函数名！！

![记得写一个函数名](按钮.png)

### Canvas

tk的绘图组件，就是绘图用的。

### Checkbutton

复选框

### Entry

单行输入框，记得打对勾。

读取的时候用 ``var.get()`` ，设置值时用 ``var.set(value)`` 。

### Frame

框架，好看。

### Label

单行文本，设置成背景色就是透明的了（笑）。

通过设置image属性可以把它变成一个图片：

```python
from PIL import Image, ImageTk

    ...
    root = tk.tk()
    #在此操作
    global img1
    img1 = ImageTk.PhotoImage(Image.open("1.png"))
    #结束操作
    top = Toplevel1 (root)
    ...
    
    ...
    #在此加入
    self.Label1.configure(image=img1)
    ...
    
```



### Labelframe

带一个标题的Frame。

### Listbox

单选列表。

### Message

自动换行的Label。

### Text

多行的文本框。

（鸽，有空再来写。

## 属性栏

改各种属性的，记得打对勾（二次）。

![记得打对勾](记得打对勾.png)

## 树状图

让你看的，能清楚地看出窗口部件的层次，没了()。

## 主菜单

~~但是我放最后才说~~

File栏：可以新建、打开、保存.tcl文件等。

Gen_Python栏：生成Python代码和Support代码（图）。

![Gen_Python](Gen_Python.png)

