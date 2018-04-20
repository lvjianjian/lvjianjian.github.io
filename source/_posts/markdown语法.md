---
title: markdown语法
date: 2017-03-24 13:12:31
tags: [markdown,语法]
categories: [markdown]
toc: false
---

## 标题

```
# 一级标题
## 二级标题
```
标题总共由6级，用1个#到6个#表示，#号后面需要跟一个空格。这里不作示例了。

***

## 列表

### 无序列表	   

```
* 1
* 2
* 3
```

用*表示无序列表，后面需要加一个空格

* 1
* 2
* 3

### 有序列表

```
1. 1
2. 2
3. 3
```
用数字加点的形式表示有序列表，注意空格。

1. 1
2. 2
3. 3
***

## 引用
```
> 这里是引用内容
```
> 这里是引用内容
***

## 链接和图片
### 链接
```
[百度](www.baidu.com "百度")
```

[百度](www.baidu.com "百度")
### 图片

```
![](http://mouapp.com/Mou_128.png)
![](markdown语法/oschina.png)
```
图片相比链接多了一个感叹号
![](http://mouapp.com/Mou_128.png)
![](markdown语法/oschina.png)

**注意:**这里我用的是hexo，需要另下插件才能把本地的图片显示出来。具体参考[http://www.tuicool.com/articles/umEBVfI](http://www.tuicool.com/articles/umEBVfI). 此外根目录下_config.yml中的post_asset_folder设置为true 
***

## 代码块
代码放入由`组成的6个点中，上下各3个

```python
def set_ch():
    mpl.rcParams['font.sans-serif'] = ['simhei'] 
    mpl.rcParams['axes.unicode_minus'] = False 
```
***


