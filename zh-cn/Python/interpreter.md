## 解释器

> **python是一门解释器语言，代码想运行，必须通过解释器执行，python存在多种解释器，分别基于不同语言开发，每个解释器都有不同的特点**

1. CPython

   python的默认解释器，是C语言开发的，所以叫CPython。也是使用最广的

2. IPython

   是基于cpython之上的一个交互式解释器，只是在交互方式上有所增强

3. PyPy

   它的目标是执行速度。对python代码进行动态编译，所以显著提高python代码的执行速度。

## GIL全局解释器锁

保证同一时刻只有一个线程对资源有操作权限（使用CPU），相当于是单线程在执行，它也是Cpython解释器的特性，所以python也被人诟病说是伪多线程

## 如何避免

可以使用多进程或者协程，或者换解释器，例如PyPy