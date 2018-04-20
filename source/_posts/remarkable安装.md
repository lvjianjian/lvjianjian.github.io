---
title: remarkable安装
date: 2017-03-24 15:09:04
tags: [remarkable,ubuntu,安装]
categories: 
 - markdown
---

今天在用typora的时候发现它在修改文档的时候有些不方便，而且现在我的显示屏也很大，完全可以用双栏的markdown编辑器。因此就决定用remarkable。
***
**首先**在[remarkable下载页(linux)](https://remarkableapp.github.io/linux/download.html "remarkable下载站")下载。 这里有deb，prm，github源码等形式。我下的是deb，因为有好多依赖问题，这种东西还是让软件帮我们解决吧。

**然后**安装
```
sudo dpkg -i remarkable_1.87_all.deb 
```
发现各种依赖不让装。然后尝试先把其中一个依赖装起来，发现它们似乎相互依赖的样子。怎么样都不行。最后其实只要这些依赖一起安装就可以了。

```
sudo apt-get install -f
```
依赖安装好了就可以安装remarkable了。

**最后**使用
```
remarkable &
```
