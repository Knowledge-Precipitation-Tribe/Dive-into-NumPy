# Dive-into-NumPy
[NumPy中文网](https://www.numpy.org.cn/)

<div><a href = "https://www.numpy.org.cn/"><image src="https://github.com/Knowledge-Precipitation-Tribe/Dive-into-numpy/blob/master/images/axis.png" alt="logo" align=center/></a></div>

## 项目介绍

本项目名为：动手学NumPy。包含以下内容

- <a href = "#NumPy简介">NumPy简介</a>
- <a href = "#NumPy数组与pthon原生数组的区别">NumPy数组与pthon原生数组的区别</a>
- <a href = "#NumPy快速入门">NumPy快速入门</a>
- <a href = "#NumPy进阶">NumPy进阶</a>
- <a href = "#numpy-100">numpy-100</a>
- <a href = "#参考文献">参考文献</a>

## [NumPy简介](#content)

NumPy是Python中科学计算的基础包。它是一个Python库，提供多维数组对象，各种派生对象（如掩码数组和矩阵），以及用于数组快速操作的各种API，有包括数学、逻辑、形状操作、排序、选择、输入输出、离散傅立叶变换、基本线性代数，基本统计运算和随机模拟等等。除其他外，它包括：

- 功能强大的N维数组对象。
- 精密广播功能函数。
- 集成 C/C+和Fortran 代码的工具。
- 强大的线性代数、傅立叶变换和随机数功能。

## [NumPy数组与pthon原生数组的区别](#content)

- NumPy 数组在创建时具有固定的大小，与Python的原生数组对象（可以动态增长）不同。更改ndarray的大小将创建一个新数组并删除原来的数组。
- NumPy 数组中的元素都需要具有相同的数据类型，因此在内存中的大小相同。 例外情况：Python的原生数组里包含了NumPy的对象的时候，这种情况下就允许不同大小元素的数组。
- NumPy 数组有助于对大量数据进行高级数学和其他类型的操作。通常，这些操作的执行效率更高，比使用Python原生数组的代码更少。
- 越来越多的基于Python的科学和数学软件包使用NumPy数组; 虽然这些工具通常都支持Python的原生数组作为参数，但它们在处理之前会还是会将输入的数组转换为NumPy的数组，而且也通常输出为NumPy数组。换句话说，为了高效地使用当今科学/数学基于Python的工具（大部分的科学计算工具），你只知道如何使用Python的原生数组类型是不够的 - 还需要知道如何使用 NumPy 数组。

## [NumPy快速入门](#content)

NumPy里有两个重要的对象：ndarray（N-dimensional array object）解决了多维数组问题，而 ufunc（universal function object）则是解决对数组进行处理的函数。

### ndarry

ndarray 实际上是多维数组的含义。在 NumPy 数组中，维数称为秩（rank），一维数组的秩为 1，二维数组的秩为 2，以此类推。在 NumPy 中，每一个线性的数组称为一个轴（axes），其实秩就是描述轴的数量。

构建ndarry：

```python
import numpy as np

a = np.array([[1, 2, 3], 
              [4, 5, 6], 
              [7, 8, 9]])
a[1,1]=10
print("shape: ", a.shape)
print("dtype: ", a.dtype)
print(a)
```

此时数组`a`就有两个轴，`0`和`1`。

<div align = "center"><image src="https://github.com/Knowledge-Precipitation-Tribe/Dive-into-numpy/blob/master/images/axis.png" width = "300" height = "200" alt="axis" align=center /></div>

当`axis=0`，该轴上的元素分为三组：

<div align = "center"><image src="https://github.com/Knowledge-Precipitation-Tribe/Dive-into-numpy/blob/master/images/axis0.png" width = "300" height = "200" alt="axis" align=center /></div>

当axis=1，该轴上的元素也同样分为三组:

<div align = "center"><image src="https://github.com/Knowledge-Precipitation-Tribe/Dive-into-numpy/blob/master/images/axis1.png" width = "300" height = "200" alt="axis" align=center /></div>

### ufunc



## [NumPy进阶](#content)



## [numpy-100](#content)

numpy-100是将numpy的常用操作整理为练习题[下载链接](https://github.com/Knowledge-Precipitation-Tribe/Dive-into-NumPy/blob/master/numpy-100.zip)，学习完以上内容可以使用此练习题检测自己的学习效果，[numpy-100原作者](https://github.com/rougier/numpy-100)。黄海广博士也对此进行了整理[numpy-100](https://github.com/fengdu78/Data-Science-Notes/tree/master/2.numpy/numpy-100)。

**使用方法** 文件夹有三个不同的ipynb文件:

1. **100_Numpy_exercises_no_solution.ipynb**

没有答案代码的文件，这个是你做的练习

2. **100_Numpy_exercises_with_hint.ipynb**

没有答案代码的文件，但有提示，这个你也可以用来练习

3. **100_Numpy_exercises.ipynb**

有答案代码和注释的文件

你可以在**100_Numpy_exercises_no_solution.ipynb** 里输入代码，看看运行结果是否和**100_Numpy_exercises.ipynb** 里面的内容一致。

## [参考文献](#content)

[1] Rakshith Vasudev: https://medium.com/hackernoon/introduction-to-numpy-1-an-absolute-beginners-guide-to-machine-learning-and-data-science-5d87f13f0d51

[2] Piotr Skalski: https://towardsdatascience.com/lets-code-a-neural-network-in-plain-numpy-ae7e74410795

[3] [https://flat2010.github.io/2017/05/31/Numpy%E6%95%B0%E7%BB%84%E8%A7%A3%E6%83%91/](https://flat2010.github.io/2017/05/31/Numpy数组解惑/)