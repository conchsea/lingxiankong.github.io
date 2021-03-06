﻿---
layout: post
title: this指针小结
category: Cpp
description: 关于c++中this指针的总结
---

前言：在 C++ 中，每一个对象都能通过 this 指针来访问自己的地址。this 指针是所有成员函数的**隐含参数**。因此，在成员函数内部，它可以用来指向调用对象。 

## 一 定义
this是一个指向自身对象的特殊指针，它并不是对象本身的一部分，不会影响sizeof（对象）的结果。
## 二 应用场景
1. this作用域是在类内部，当在类的非静态成员函数中访问类的非静态成员的时候，编译器会自动将对象本身的地址作为一个隐含参数传递给函数。它作为非静态成员函数的隐含形参，对各成员的访问均通过this进行。
2. 在类的非静态成员函数中返回类对象本身的时候，直接使用 return *this；
3. 当参数与成员变量名相同时使用this指针指向成员变量，例如this->n = n （不能写成n = n）。
## 三 注意事项
1. 友元函数没有this指针，因为友元不是类的成员。只有成员函数才有 this 指针。    
2. this指针只能在一个类的成员函数中调用，它表示当前对象的地址。(全局函数，静态函数都不能使用this。)
3. this在成员函数的开始前构造的，在成员的结束后清除。这个生命周期同任一个函数的参数是一样的，没有任何区别。当调用一个类的成员函数时，编译器将类的指针作为函数的this参数传递进去。





* 参考：[百度百科C++this指针词条](https://baike.baidu.com/item/C++this%E6%8C%87%E9%92%88/637012)