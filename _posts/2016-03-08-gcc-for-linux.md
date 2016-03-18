---
layout: post
title: gcc for Linux
---

{{ page.title }}
===============

C语言是Linux下使用最多的语言，也是最基础的语言。在Linux中，最常用的C语言编译器是GCC（GNU Compiler Collection），它支持多种语言，功能强大。这里简单介绍一下其基本使用过程。
使用GCC编译程序时，编译过程被细分为四个阶段：
1. 预处理(Pre-Processing)   
2. 编译(Compiling)   
3. 汇编(Assembling)   
4. 链接(Linking）   

一个程序的完整编写、编译过程如下：      

##写好源程序代码   
以Centos为例，先进入家目录，编写源程序代码。   
``` cd /home  
``` mkdir c   
``` cd c   
``` vi test.c    
这里需要了解vi的基本使用，可以参考这里：[vi/vim使用方法](http://www.itskys.com/2016/03/02/vi-vim.html)
然后在源程序代码中输入代码，示例如下：   
```   
	#include <stdio.h>
	int main(void) {
		printf("Hello World, This is my first C Programming in Linux!\n");
		return 0;
	}
```   

然后保存该文件（先按ESC键，然后按:wq即可保存退出）。   
可以使用ls命令查看一下文件信息。   

##编译并运行   
执行以下命令即可编译和执行程序：   
``` gcc test.c -o test  //把test.c编译、链接为test可执行文件    
``` ./test   //执行   

如果一切正常，会有以下显示结果：  
``` Hello World, This is my first C Programming in Linux!   

但是，写程序不可能总是那么一帆风顺，一次过关，可能会有各种错误、Bug，所以，更多地，我们需要一步步来操作。

##分步操作

假设test.c已经写好，第一步需要进行的是：

* 预编译
命令如下：
``` gcc -E test.c -o test.i   
这时，会在目录下生成一个test.i文件，如果查看其内容，可看到<stdio.h>的内容已经被插入。

接下来要把test.i(也称为中间文件)编译为目标代码，即：

* 编译
执行以下命令：
``` gcc -c test.i -o test.o   
这时，可以用ls命令查看一下目录，其中多了一个文件test.o文件，也可以查看其内容。
第三步，将目标文件链接成可执行文件，即：

* 链接
命令如下：
``` gcc test.o -o test  

这时，目录下会生成一个test文件（没有扩展名），它就是程序的可执行文件，执行方法为：
``` ./test   

中间也可以生成汇编程序输出，只需要使用-S选项即可。如:
``` gcc -S test.i -o test.s   
然后再把编译test.s即可。


如果要把多个源程序文件编译链接为一个可执行程序，可以组合执行：

``` gcc a.c b.c d.c -o abc  
对于编译器，它其实是把每个源程序执行了一次预处理--编译--链接的过程。








