# **Numpy**

## 1.导入numpy库

```py
import numpy as np
```

## 2.创建数组和矩阵

NumPy 数组： NumPy 数组是 NumPy 中最基本的数据结构，用于存储数值数据。可以使用 `np.array()` 函数创建一个 NumPy 数组。

```python
a = np.array([1, 2, 3])
print(a)  # 输出：array([1, 2, 3])
```

NumPy 数组的属性： NumPy 数组的属性包括数组的形状、数据类型、元素数量等。可以使用 `shape`、`dtype` 和 `size` 属性分别获取这些属性。

```py
a = np.array([[1, 2], [3, 4]])
print(a.shape)  # 输出： (2, 2)
print(a.dtype)  # 输出： int64
print(a.size)  # 输出： 4
```

NumPy 数组的索引和切片： NumPy 数组可以使用索引和切片进行访问和操作。可以使用 `[]` 操作符进行索引和切片。

```python
a = np.array([[1, 2], [3, 4]])
print(a[0, 0])  # 输出： 1
print(a[0, :])  # 输出： array([1, 2])
print(a[:, 0])  # 输出： array([1, 3])
```

NumPy 数组的运算： NumPy 数组支持各种数学运算，包括加法、减法、乘法、除法等。可以使用 NumPy 提供的数学函数进行运算。

```python
a = np.array([1, 2, 3])
b = np.array([4, 5, 6])
print(a + b)  # 输出： array([5, 7, 9])
print(a * b)  # 输出： array([4, 10, 18])
```

NumPy 数组的广播： NumPy 数组的广播是指 NumPy 数组在不同形状之间进行数学运算时，自动调整数组形状以使它们兼容的方法

```python
a = np.array([[1, 2], [3, 4]])
b = np.array([1, 2])
print(a + b)  # 输出： array([[2, 4], [4, 6]])
```

NumPy 数组的切片和转置： NumPy 数组可以使用切片和转置进行操作。

```python
a = np.array([[1, 2, 3], [4, 5, 6]])
print(a[0, :2])  # 输出： array([1, 2])
print(a[:, 1:])  # 输出： array([[2, 3], [5, 6]])
```

NumPy 数组的排序和搜索： NumPy 数组可以使用 `sort()` 方法进行排序，可以使用 `argsort()` 方法进行索引排序。可以使用 `argmin()` 和 `argmax()` 方法进行最小值和最大值索引查找。

```python
a = np.array([3, 1, 4, 1, 5, 9])
print(np.sort(a))  # 输出： array([1, 1, 3, 4, 5, 9])
print(np.argsort(a))  # 输出： array([1, 2, 0, 4, 5, 3])
print(a[np.argmin(a)])  # 输出： 1
print(a[np.argmax(a)])  # 输出： 9
```

NumPy 数组的统计函数： NumPy 提供了许多统计函数，如均值、方差、标准差、最大值、最小值等。可以使用 `mean()`、`std()`、`var()`、`max()`、`min()` 等函数进行计算

```python
a = np.array([1, 2, 3, 4, 5])
print(np.mean(a))  # 输出： 3.0
print(np.std(a))  # 输出： 1.4142135623730951
print(np.var(a))  # 输出： 1.4142135623730951
print(np.max(a))  # 输出： 5
print(np.min(a))  # 输出： 1
```

NumPy 数组的绘图： NumPy 提供了 `matplotlib` 模块的接口，可以使用 `matplotlib` 进行数据可视化。

```py
import matplotlib.pyplot as plt

a = np.array([1, 2, 3, 4, 5])
plt.plot(a)
plt.show()
```



## 3.线性代数运算

矩阵乘法： 矩阵乘法可以使用 `dot()` 函数进行。

```python
a = np.array([[1, 2], [3, 4]])
b = np.array([[5, 6], [7, 8]])
c = np.dot(a, b)
print(c)  # 输出： array([[19, 22], [43, 50]])
```

矩阵分解： NumPy 提供了多种矩阵分解方法，如 QR 分解、LU 分解、Cholesky 分解等。

```python
a = np.array([[1, 2], [3, 4]])
q, r = np.linalg.qr(a)
print(q)  # 输出： array([[-0.70710678, -0.70710678], [0.70710678, -0.70710678]])
print(r)  # 输出： array([[1.41421356, 0.], [0., 1.41421356]])
```

行列式： 行列式可以使用 `det()` 函数进行计算。

```python
a = np.array([[1, 2], [3, 4]])
print(np.linalg.det(a))  # 输出： -2.0
```

矩阵的的特征值和特征向量： 矩阵的特征值和特征向量可以使用 `eig()` 函数进行计算。

```python
a = np.array([[1, 2], [3, 4]])
values, vectors = np.linalg.eig(a)
print(values)  # 输出： array([-1.+0.j, -0.+1.j])
print(vectors)  # 输出： array([[-0.70710678, -0.70710678], [0.70710678, -0.70710678]])
```

矩阵的行列式和行列式： 矩阵的行列式和行列式可以使用 `linalg.det()` 和 `linalg.inv()` 函数进行计算。

```python
a = np.array([[1, 2], [3, 4]])
print(np.linalg.det(a))  # 输出： -2.0
print(np.linalg.inv(a))  # 输出： array([[-2. ,  1. ], [ 1. , -2. ]])
```



## 4.四种乘法

1. `a*b`  :对应元素相乘
2. `np.dot(a,b)` :矩阵的标准乘法
3. `a@b`：等价于`np.dot(a,b)`
4. `np.multiply` 是 NumPy 中的一个函数，用于执行元素级别的乘法操作。它与 `*` 操作符的效果相同，但 `np.multiply` 可以应用于多维数组和矩阵

```python
import numpy as np

A = np.array([[1, 2], [3, 4]])
B = np.array([[5, 6], [7, 8]])

print(A @ B)
'''
[[19 22]
[43 50]]
'''
print(np.dot(A, B))
'''
[[19 22]
[43 50]]
'''
print(A * B)
'''
[[ 5 12]
[21 32]]
'''

```

```python
import numpy as np

a = np.array([1, 2, 3, 4, 5])

#计算数组中所有元素的乘积：
product_a = np.multiply.reduce(a)
print(product_a)  # 输出：120

#计算矩阵中所有元素的乘积：
product_b = np.multiply.reduce(b)
print(product_b)  # 输出：243


#计算数组中指定轴上元素的总和：
product_a_row = np.multiply(a, np.array([1, 2, 3]))
print(product_a_row)  # 输出：[1 4 9 16 27]
product_a_col = np.multiply(a.T, np.array([1, 2, 3]))
print(product_a_col)  # 输出：[1 4 9 16 27]


#计算矩阵中指定轴上元素的总和：
product_b_row = np.multiply(b, np.array([1, 2, 3]))
print(product_b_row)  # 输出：[1 4 9 16 27]
product_b_col = np.multiply(b.T, np.array([1, 2, 3]))
print(product_b_col)  # 输出：[1 4 9 16 27]	
```



## 5.所有元素总和

np.sum()

```python
import numpy as np

a = np.array([1, 2, 3, 4, 5])
b = np.array([[1, 2, 3], [4, 5, 6], [7, 8, 9]])

#计算数组中所有元素的总和
sum_a = np.sum(a)
print(sum_a)  # 输出：15


#计算矩阵中所有元素的总和
sum_b = np.sum(b)
print(sum_b)  # 输出：45


#计算数组中指定轴上元素的总和：
sum_a_row = np.sum(a, axis=0)
print(sum_a_row)  # 输出：[12 15 18]
sum_a_col = np.sum(a, axis=1)
print(sum_a_col)  # 输出：[6 17 28]


#计算矩阵中指定轴上元素的总和：
sum_b_row = np.sum(b, axis=0)
print(sum_b_row)  # 输出：[12 15 18]
sum_b_col = np.sum(b, axis=1)
print(sum_b_col)  # 输出：[6 17 28]
```

