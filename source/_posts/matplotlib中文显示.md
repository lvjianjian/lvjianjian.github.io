---
title: matplotlib中文显示
date: 2017-03-24 13:08:51
tags: [python,matplotlib,中文显示]
categories: [python]
---



# matplotlib中文显示
今天在ubuntu下用matplotlib显示中文的时候出现了乱码，之前在windows上用了下面这段代码就可以了。
```python
def set_ch():
    mpl.rcParams['font.sans-serif'] = ['simhei'] # 指定默认字体
    mpl.rcParams['axes.unicode_minus'] = False # 解决保存图像是负号'-'显示为方块的问题
```
但是在ubuntu上还是显示不出。主要原因是ubuntu上没有这个字体。所以从windows上把黑体字体搬到ubuntu的下面这个路径下。
```
/usr/local/lib/python2.7/dist-packages/matplotlib/mpl-data/fonts
```
可能每台机子具体路径不太一样，需要自己找下。我是通过`print matplotlib.__file__`找到的。

然后删除~/.cache/matplotlib的缓冲目录就可以了。