# Dive-into-NumPy
[NumPy中文网](https://www.numpy.org.cn/)

<div><a href = "https://www.numpy.org.cn/"><image src="https://github.com/Knowledge-Precipitation-Tribe/Dive-into-numpy/blob/master/images/NumPy_logo.png" alt="logo" align=center/></a></div>

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

- <a href = "#ndarry">ndarry</a>
- <a href = "#ufunc">ufunc</a>
  - <a href = "#连续数组的创建">连续数组的创建</a>
  - <a href = "#算术运算">算术运算</a>
  - <a href = "#统计函数">统计函数</a>
  - <a href = "#排序函数">排序函数</a>

### [ndarry](#content)

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
print("a: \n", a)
print("a[:, 1]: \n", a[:,1])
```

输出结果：

```python
shape:  (3, 3)
dtype:  int64
a: 
 [[ 1  2  3]
 [ 4 10  6]
 [ 7  8  9]]
a[:, 1]: 
 [ 2 10  8]
```



此时数组`a`就有两个轴，`0`和`1`。

<div align = "center"><image src="https://github.com/Knowledge-Precipitation-Tribe/Dive-into-numpy/blob/master/images/axis.png" width = "300" height = "200" alt="axis" align=center /></div>

当`axis=0`，该轴上的元素分为三组：

<div align = "center"><image src="https://github.com/Knowledge-Precipitation-Tribe/Dive-into-numpy/blob/master/images/axis0.png" width = "300" height = "200" alt="axis" align=center /></div>

当axis=1，该轴上的元素也同样分为三组:

<div align = "center"><image src="https://github.com/Knowledge-Precipitation-Tribe/Dive-into-numpy/blob/master/images/axis1.png" width = "300" height = "200" alt="axis" align=center /></div>

### [ufunc](#content)

ufunc 是 universal function 的缩写，是不是听起来就感觉功能非常强大？确如其名，它能对数组中每个元素进行函数操作。NumPy 中很多 ufunc 函数计算速度非常快，因为都是采用 C 语言实现的。

#### [连续数组的创建](#content)

```python
import numpy as np

x1 = np.arange(1,11,2) #参数为：起始值，终止值，步长（不包括终止值）
x2 = np.linspace(1,9,5) #参数为：起始值，终止值，元素个数（包括终止值）
```

#### [算术运算](#content)

```python
import numpy as np

x1 = np.arange(1,11,2)
x2 = np.linspace(2,10,5)

print("x1: \n", x1)
print("x2: \n", x2)
print("add: \n", np.add(x1, x2)) #加
print("subtract: \n", np.subtract(x1, x2))#减
print("multiply: \n", np.multiply(x1, x2))#乘
print("divide: \n", np.divide(x1, x2))#除
print("power: \n", np.power(x1, x2))#求幂
print("remainder: \n", np.remainder(x1, x2))#取余
```

输出结果：

```python
x1: 
 [1 3 5 7 9]
x2: 
 [ 2.  4.  6.  8. 10.]
add: 
 [ 3.  7. 11. 15. 19.]
subtract: 
 [-1. -1. -1. -1. -1.]
multiply: 
 [ 2. 12. 30. 56. 90.]
divide: 
 [0.5        0.75       0.83333333 0.875      0.9       ]
power: 
 [1.0000000e+00 8.1000000e+01 1.5625000e+04 5.7648010e+06 3.4867844e+09]
remainder: 
 [1. 3. 5. 7. 9.]
```

#### [统计函数](#content)

```python
#统计矩阵中的最大值与最小值
import numpy as np

a = np.array([[8,6,1],
              [2,4,7],
              [3,9,5]])
print("a: \n", a)
print("min: \n", np.amin(a))#整个矩阵中最小值
print("axis=0 min: \n", np.amin(a,axis=0))#axis=0方向的最小值
print("axis=1 min: \n", np.amin(a,axis=1))#axis=1方向的最小值
#max与此相同
print("median： \n", np.median(a))#求中位数
print("mean: \n", np.mean(a))#求均值
print("average: \n", np.average(a))#求平均值
print("std: \n", np.std(a))#求标准差
print("var: \n", np.var(a))#求方差
```

输出结果：

```python
a: 
 [[8 6 1]
 [2 4 7]
 [3 9 5]]
min: 
 1
axis=0 min: 
 [2 4 1]
axis=1 min: 
 [1 2 3]
median： 
 5.0
mean: 
 5.0
average: 
 5.0
std: 
 2.581988897471611
var: 
 6.666666666666667
```

#### [排序函数](#content)

```python
import numpy as np

a = np.array([[4,3,2],
              [2,4,1]])
print("a: \n", a)
print("sort: \n", np.sort(a))
print("axis=None sort:\n", np.sort(a, axis=None))
print("axis=0 sort: \n", np.sort(a, axis=0))
print("axis=1 sort: \n", np.sort(a, axis=1))
```

输出结果：

```python
a: 
 [[4 3 2]
 [2 4 1]]
sort: 
 [[2 3 4]
 [1 2 4]]
axis=None sort:
 [1 2 2 3 4 4]
axis=0 sort: 
 [[2 3 1]
 [4 4 2]]
axis=1 sort: 
 [[2 3 4]
 [1 2 4]]
```

## [NumPy进阶](#content)

NumPy进阶操作请查看：[链接]()

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

[3] [https://flat2010.github.io/2017/05/31/Numpy数组解惑](https://flat2010.github.io/2017/05/31/Numpy数组解惑/)