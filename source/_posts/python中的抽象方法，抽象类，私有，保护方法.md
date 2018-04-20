---
title: python中的抽象方法，抽象类，私有，保护方法
date: 2017-04-06 15:50:32
tags: [python,抽象]
categories: python
---

平时在python基本不怎么写类，都是定义方法到处调用。但是感觉把公共逻辑封装成抽象类，再继承写独立的逻辑更快更清晰。
由于python 没有抽象类、接口的概念，所以要实现这种功能得abc.py 这个类库,具体方式如下：
```python
from abc import ABCMeta, abstractmethod

class abstract1(object):
    __metaclass__ = ABCMeta

    @abstractmethod
    def print1(self):pass

    def print2(self):
        print "Test1 print2"

    def __si(self):
        print "abstract1 si"

    def gong(self):
        print "abstarct gong"

    def _pro(self):
        print "abstract pro"

class imp1(abstract1):
    __metaclass__ = ABCMeta

    def print1(self):
        print "imp1 pring1"

    def imp_si(self):
        abstract1.gong()
        abstract1._pro()
```

`_metaclass__ = ABCMeta`可以保证在实例化一个抽象类的时候抛出异常。

`@abstractmethod`放在要定义的抽象方法上。

私有方法用2个下划线定义，如`__private_functon()`，子类无法调用。

保护方法用1个下划线定义，如`_protected_function()`，子类可以调用。