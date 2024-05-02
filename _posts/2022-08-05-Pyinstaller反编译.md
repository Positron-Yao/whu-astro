---
layout: mypost
title: Pyinstaller反编译
categories: [Python]
---

## 用Pyinstaller实现python程序打包

```powershell
pyinstaller -F(生成文件) -D(生成文件夹) ***.py -w(是否显示cmd黑框框) -i(图标) ***.ico
```

之后程序会生成一堆文件，在dist文件夹中可报找到与源文件同名的``***.exe``

## 反编译过程

工具：pyinstxtractor.py，uncompyle6(好像不支持太高的版本？)

在[pyinstxtractor的github页面](https://github.com/extremecoders-re/pyinstxtractor)下载pyinstxtractor.py后，用``instxtractor.py ***.exe``实现解包，会生成一个文件夹，在文件夹中找到一个无扩展名的``[原文件名]``文件和``struct``文件。  

打开``struct``和``[原文件名]``文件(十六进制)，将``struct``的前**16个字符**复制到``[原文件名]``开头(pyinstxtractor的一个小问题，缺了一点)。

若原程序有import的模块，可在同目录下的``PYZ-00.pyz_extracted``文件夹中找到``***.pyc``，用``struct``的前**16个字符**代替``***.pyc``的前**12个字符**(麻烦)。

获得所需的``.pyc``后，用``pip install uncompyle6``安装，安装后找到``%python_home%\Lib\site-packages\xdis\magics.py``，搜索``add_canonic_versions``函数(适配版本)，找一下有没有当前Python版本，没有的话加上。

用``uncompyle6 -o out.py source.pyc``格式完成``.pyc``的反编译。

从[这里](https://zhuanlan.zhihu.com/p/109266820)学的。

End.