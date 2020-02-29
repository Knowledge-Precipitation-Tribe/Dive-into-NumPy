# Dive-into-NumPy
[NumPy中文网](https://www.numpy.org.cn/)

![numpy_logo](https://github.com/Knowledge-Precipitation-Tribe/Dive-into-numpy/blob/master/images/NumPy_logo.png)

## NumPy简介

NumPy是Python中科学计算的基础包。它是一个Python库，提供多维数组对象，各种派生对象（如掩码数组和矩阵），以及用于数组快速操作的各种API，有包括数学、逻辑、形状操作、排序、选择、输入输出、离散傅立叶变换、基本线性代数，基本统计运算和随机模拟等等。除其他外，它包括：

- 功能强大的N维数组对象。
- 精密广播功能函数。
- 集成 C/C+和Fortran 代码的工具。
- 强大的线性代数、傅立叶变换和随机数功能。

## NumPy数组与pthon原生数组的区别

- NumPy 数组在创建时具有固定的大小，与Python的原生数组对象（可以动态增长）不同。更改ndarray的大小将创建一个新数组并删除原来的数组。
- NumPy 数组中的元素都需要具有相同的数据类型，因此在内存中的大小相同。 例外情况：Python的原生数组里包含了NumPy的对象的时候，这种情况下就允许不同大小元素的数组。
- NumPy 数组有助于对大量数据进行高级数学和其他类型的操作。通常，这些操作的执行效率更高，比使用Python原生数组的代码更少。
- 越来越多的基于Python的科学和数学软件包使用NumPy数组; 虽然这些工具通常都支持Python的原生数组作为参数，但它们在处理之前会还是会将输入的数组转换为NumPy的数组，而且也通常输出为NumPy数组。换句话说，为了高效地使用当今科学/数学基于Python的工具（大部分的科学计算工具），你只知道如何使用Python的原生数组类型是不够的 - 还需要知道如何使用 NumPy 数组。

## NumPy快速入门



## NumPy进阶



## numpy-100

numpy-100是将numpy的常用操作整理为练习题，学习完以上内容可以使用此练习题检测自己的学习效果，[numpy-100原作者](https://github.com/rougier/numpy-100)。也可参考黄海广整理的[numpy-100](https://github.com/fengdu78/Data-Science-Notes/tree/master/2.numpy/numpy-100)。





