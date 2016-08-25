Python数据分析 - NumPy入门
===

林应（微博：[Bear-彼德洛维奇](http://weibo.com/p/1005052607195824/)）
Github: 
2016/08/27

---
# 简介

- NumPy是Python语言的一个扩充程序库。支持高级大量的维度数组与矩阵运算，此外也针对数组运算提供大量的数学函数库。
- 官网链接：TODO
- 作者介绍
  - [Jim Hugunin](https://www.linkedin.com/in/jimhugunin)
  - [Travis Oliphant](https://www.linkedin.com/in/jimhugunin)

---
# NumPy提供的功能
- 快速高效的多维数组对象ndarray
- 用于对数组执行元素级计算以及直接对数组执行数学运算的函数
- 用于读写硬盘上基于数组的数据集的工具
- 线性代数运算、傅里叶变换，以及随机数生成
- 用于将C、C++、Fortran代码集成到Python的工具
- 除了为Python提供快速的数组处理能力，NumPy在数据分析方面还有另外一个主要作用，即作为在算法之间传递数据的容器。

---
# 效率对比
- 三种数据结构：list, array, numpy
- 三种操作：for, sum, numpy.sum
- 例子代码：<small>perf_compare.py<small>

---
# 多维数组对象ndarray
**创建ndarray**
|函数|说明|
|:--|:--|
|<small>array</small>|<small>将输入数据（列表、元组、数组或其它序列类型）转换为ndarray。要么推断出dtype，要么显示指定dtype。默认直接复制输入数据。</small>|
|<small>asarray</small>|<small>将输入转换为darray，如果输入本身就是一个ndarray就不进行复制。</small>|
|<small>arange</small>|<small>类似于内置的range，但返回一个ndarray而不是列表。</small>|

---
# 多维数组对象ndarray
**创建ndarray**
|函数|说明|
|:--|:--|
|<small>ones, ones_like</small>|<small>根据指定形状和dtype创建一个全1数组。ones_like以另一个数组为参数，并根据其形状和dtype创建一个全1数组。</small>|
|<small>zeros, zeros_like</small>|<small>类似于ones和ones_like，只不过产生的是全0数组而已。</small>|
|<small>empty, empty_like</small>|<small>创建数组，只分配内存空间但不填充任何值。</small>|
|<small>eype, identity</small>|<small>创建一个正方的N * N单位矩阵</small>|

---
# 多维数组对象ndarray
**创建ndarray**
- 例子代码: <small>the_numpy_ndarray/creating_ndarray.py</small>

---
# 多维数组对象ndarray
**NumPy数据类型**
|类型|类型代码|说明|
|:--|:--|:--|
|<small>int8, uint8</small>|<small>i1, u1</small>|<small>有／无符号的8位整型</small>|
|<small>int16, uint16</small>|<small>i2, u2</small>|<small>有／无符号的16位整型</small>|
|<small>int32, uint32</small>|<small>i4, u4</small>|<small>有／无符号的32位整型</small>|
|<small>int64, uint64</small>|<small>i8, u8</small>|<small>有／无符号的64位整型</small>|
|<small>float16</small>|<small>f2</small>|<small>半精度浮点数</small>|

---
# 多维数组对象ndarray
**NumPy数据类型**
|类型|类型代码|说明|
|:--|:--|:--|
|<small>float32</small>|<small>f4或f</small>|<small>标准的单精度浮点数，与C的float兼容。</small>|
|<small>float64</small>|<small>f8或d</small>|<small>标准的双精度浮点数。与C的double和Python的float兼容。</small>|
|<small>float128</small>|<small>f16或g</small>|<small>扩展精度浮点数</small>|
|<small>complex64/128/256</small>|<small>c8/16/32</small>|<small>分别用两个32位，64位或128位浮点数表示的复数。</small>|

---
# 多维数组对象ndarray
**NumPy数据类型**
|类型|类型代码|说明|
|:--|:--|:--|
|<small>bool</small>|<small>?</small>|<small>存储True和False值的布尔类型</small>|
|<small>onject</small>|<small>O</small>|<small>Python对象类型</small>|
|<small>string_</small>|<small>S</small>|<small>固定长度的字符串类型。S10代表长度为10的字符串。</small>|
|<small>unicode_</small>|<small>U</small>|<small>固定长度的unicode类型</small>|

---
# 多维数组对象ndarray
**NumPy数据类型**
- 创建ndarray时指定dtype类型
- 使用astype显示转换类型
- 例子代码: <small>the_numpy_ndarray/data_types_for_ndarray.py</small>

---
# 多维数组对象ndarray
**数组和标量之间的运算**
- 不用编写循环即可对数据执行批量运算
- 大小相等的数组之间的任何算术运算都会将运算应用到元素级
- 数组与标量的算术运算也会将那个标量值传播到各个元素
- 例子代码: <small>the_numpy_ndarray/operations_between_arrays_and_scalars.py</small>

---
# 多维数组对象ndarray
**基本的索引和切片**
- 索引原理
- 切片原理
- 例子代码: <small>the_numpy_ndarray/basic_indexing_and_slicing.py</small>

---
# 多维数组对象ndarray
**布尔型索引**
- 布尔型数组的长度必须跟被索引的轴长度一致。
-  可以将布尔型数组跟切片、整数（或整数序列）混合使用
- 例子代码: <small>the_numpy_ndarray/boolean_indexing.py</small>

---
# 多维数组对象ndarray
**花式索引**
- 花式索引（Fancy indexing）是一个NumPy术语，它指的是利用整数数组进行索引。
- 一次传入多个索引数组会有一点特别。它返回的是一个一维数组，其中的元素对应各个索引元组
- 例子代码: <small>the_numpy_ndarray/fancy_indexing.py</small>

---
# 多维数组对象ndarray
**数组转置和轴对换**
- 一维／二维数组转置
- 高维数组轴对换
- 例子代码: <small>the_numpy_ndarray/transposing_arrays_and_swapping_axes.py</small>

---
# 快速的元素级数组函数
**一元函数**
|函数|说明|
|:--|:--|
|<small>abs, fabs</small>|<small>计算整数、浮点数或复数的绝对值。对于非复数值，可以使用更快的fabs。</small>|
|<small>sqrt</small>|<small>计算各元素的平方根。相当于arr ** 0.5</small>|
|<small>square</small>|<small>计算各元素的平方。相当于arr ** 2</small>|
|<small>exp</small>|<small>计算各元素的e^x</small>|
|<small>log, log10, log2, log1p</small>|<small>分别为自然对数、底数为10的log、底数为2的log和log(1 + x)。</small>|

---
# 快速的元素级数组函数
**一元函数**
|函数|说明|
|:--|:--|
|<small>sign</small>|<small>计算各元素的正负号：1（正数）、0（零）、－1（负数）。</small>|
|<small>ceil</small>|<small>计算各元素的ceiling值，即大于等于该值的最小整数。</small>|
|<small>floor</small>|<small>计算各元素的floor值，即小于等于该值的最小整数。</small>|
|<small>rint</small>|<small>将各元素值四舍五入到最接近的整数，保留dtype。</small>|
|<small>modf</small>|<small>将数组的小数部分与整数部分以两个独立数组的形式返还。</small>|

---
# 快速的元素级数组函数
**一元函数**
|函数|说明|
|:--|:--|
|<small>isnan</small>|<small>返回一个表示“哪些值是NaN（这不是一个数字）”的布尔型数组</small>|
|<small>isfinite, isinf</small>|<small>分别返回一个表示“哪些元素是有限的（非inf，非NaN）”或“哪些元素是无穷的”的布尔型数组</small>|
|<small>cos, cosh, sin, sinh, tan, tah</small>|<small>普通型或双取型三角函数</small>|

---
# 快速的元素级数组函数
一元函数
|函数|说明|
|:--|:--|
|<small>arccos, arccosh, arcsin, arcsinh, arctan, arctanh</small>|<small>反三角函数</small>|
|<small>logical_not</small>|<small>计算各元素not x的真值。相当于-arr。</small>|

---
# 快速的元素级数组函数
二元函数
|函数|说明|
|:--|:--|
|<small>add</small>|<small>将数组中对应的元素相加</small>|
|<small>subtract</small>|<small>从第一个数组中减去第二个数组中的元素</small>|
|<small>multiply</small>|<small>数组元素相乘</small>|
|<small>divide, floor_divide</small>|<small>除法或向下取整除法</small>|
|<small>power</small>|<small>对第一个数组中的元素A和第二个数组中对应位置的元素B，计算A^B。</small>|

---
# 快速的元素级数组函数
**二元函数**
|函数|说明|
|:--|:--|
|<small>maximum, fmax</small>|<small>元素级的最大值计算。fmax将忽略NaN。</small>|
|<small>minimum, fmix</small>|<small>元素级的最小值计算。fmax将忽略NaN。</small>|
|<small>mod</small>|<small>元素级的求模计算</small>|
|<small>copysign</small>|<small>将第二个数组中的符号复制给第一个数组中的值。</small>|

---
# 快速的元素级数组函数
**二元函数**
|函数|说明|
|:--|:--|
|<small>greater, greater_equal, less, less_equal, equal, not_equal</small>|<small>执行元素级的比较，最终产生布尔型数组。</small>|
|<small>logical_and, logical_or, logical_xor</small>|<small>执行元素级的真值逻辑运算，最终产生布尔型数组。</small>|

- 例子代码: universal_functions.py

---
# 利用数组进行数据处理
**简介**
- NumPy数组使你可以将许多种数据处理任务表述为简洁的数组表达式（否则需要编写循环）。用数组表达式代替循环的做法，通常被称为矢量化。
- 矢量化数组运算要比等价的纯Python方式快上一两个数量级
- 例子代码：<small>data_processing_using_arrays/intro.py</small>

---
# 利用数组进行数据处理
**将条件逻辑表述为数组运算**
- 列表推导的局限性
  - 纯Python代码，速度不够快。
  -  无法应用于高维数组
- where和where的嵌套
- 例子代码: <small>data_processing_using_arrays/expressing_conditional_logic_as_array_operations.py</small>

---
# 利用数组进行数据处理
**数学和统计方法**
|函数|说明|
|:--|:--|
|<small>sum</small>|<small>对数组中全部或某轴向的元素求和。零长度的数组的sum为0。</small>|
|<small>mean</small>|<small>算术平均数。零长度的数组的mean为NaN。</small>|
|<small>std, var</small>|<small>分别为标准差和方差，自由度可调（默认为n）。</small>|
|<small>min, max</small>|<small>最大值和最小值</small>|
|<small>argmin, argmax</small>|<small>分别为最大值和最小值的索引</small>|

---
# 利用数组进行数据处理
**数学和统计方法**
|函数|说明|
|:--|:--|
|<small>cumsum</small>|<small>所有元素的累计和</small>|
|<small>cumprod</small>|<small>所有元素的累计积</small>|

- 标准差和方差的解释
- cumsum和cumprod的解释
- 带axis参数的统计函数
- 例子代码: <small>data_processing_using_arrays/mathematical_and_statistical_methods.py</small>

---
# 利用数组进行数据处理
**用于布尔型数组的方法**
- sum对True值计数
- any和all测试布尔型数组，对于非布尔型数组，所有非0元素将会被当做True。
- 例子代码: <small>data_processing_using_arrays/methods_for_boolean_arrays.py</small>

---
# 利用数组进行数据处理
**排序**
- 直接排序
- 指定轴排序
- 例子代码: <small>data_processing_using_arrays/sorting.py</small>

---
# 利用数组进行数据处理
**去重以及其它集合运算**
|函数|说明|
|:--|:--|
|<small>unique(x)</small>|<small>计算x中的唯一元素，并返回有序结果。</small>|
|<small>intersect1d(x, y)</small>|<small>计算x和y中的公共元素，并返回有序结果。</small>|
|<small>union1d(x, y)</small>|<small>计算x和y的并集，并返回有序结果。</small>|
|<small>in1d(x, y)</small>|<small>得到一个表述"x的元素是否包含于y"的布尔型数组</small>|

---
# 利用数组进行数据处理
去重以及其它集合运算
|函数|说明|
|:--|:--|
|<small>setdiff1d(x, y)</small>|<small>集合的差，即元素在x中且不在y中</small>|
|<small>setor1d(x, y)</small>|<small>集合的异或，即存在于一个数组中但不同时存在于两个数组中的元素。</small>|

- 例子代码: <small>data_processing_using_arrays/unique_and_other_set_logic.py</small>

---
# 数组文件的输入输出

- 将数组以二进制格式保存到磁盘
- 存取文本文件
- 例子代码
  - <small>file_input_and_output_with_arrays/saving_and_loading_text_files.py</small>
  - <small>file_input_and_output_with_arrays/storing_arrays_on_disk_in_binary_format.py</small>

---
# 线性代数
|函数|说明|
|:--|:--|
|<small>diag</small>|<small>以一维数组的形式返回方阵的对角线（或非对角线元素），获奖一维数组转换为方阵（非对角线元素为0）。</small>|
|<small>dot</small>|<small>矩阵乘法</small>|
|<small>trace</small>|<small>计算对角线元素的和</small>|
|<small>det</small>|<small>计算矩阵行列式</small>|
|<small>eig</small>|<small>计算方阵的特征值和特征向量</small>|
|<small>inv</small>|<small>计算方阵的逆</small>|
 
---
# 线性代数
|函数|说明|
|:--|:--|
|<small>pinv</small>|<small>计算矩阵的Moore-Penrose伪逆</small>|
|<small>qr</small>|<small>计算QR分解</small>|
|<small>svd</small>|<small>计算奇异值分解</small>|
|<small>solve</small>|<small>解线性方程Ax = b，其中A为一个方阵。</small>|
|<small>lstsq</small>|<small>计算Ax = b的最小二乘解</small>|

- 例子代码: <small>linear_algebra.py</small>

---
# 随机数生成
|函数|说明|
|:--|:--|
|<small>seed</small>|<small>确定随机数生成器的种子</small>|
|<small>permutation</small>|<small>返回一个序列的随机排列或返回一个随机排列的返回</small>|
|<small>shuffle</small>|<small>对一个序列就地随机乱序</small>|
|<small>rand</small>|<small>产生均匀分布的样本值</small>|
|<small>randint</small>|<small>从给定的上下限范围内随机选取整数</small>|

---
# 随机数生成
|函数|说明|
|:--|:--|
|<small>randn</small>|<small>产生正态分布（平均值为0，标准差为1）</small>|
|<small>binomial</small>|<small>产生二项分布的样本值</small>|
|<small>normal</small>|<small>产生正态（高斯）分布的样本值</small>|
|<small>beta</small>|<small>产生Beta分布的样本值</small>|
|<small>chisquare</small>|<small>产生卡方分布的样本值</small>|

---
# 随机数生成
|函数|说明|
|:--|:--|
|<small>gamma</small>|<small>产生伽马分布的样本值</small>|
|<small>uniform</small>|<small>产生在[0, 1]中均匀分布的样本值</small>|

- 几种分布的解释：二项，正态，Beta，伽马。
- 例子代码: <small>random_number_generation.py</small>

---
# 高级应用
**数组重塑**
- reshape 重塑数组
- -1自动推导维度大小
- 例子代码: <small>advanced_array_manipulation/reshaping_arrays.py</small>

---
# 高级应用
**数组的合并和拆分**
|函数|说明|
|:--|:--|
|<small>concatenate</small>|<small>最一般化的连接，沿一条轴连接一组数组</small>|
|<small>vstack, row_stack</small>|<small>以面向行的方式对数组进行堆叠（沿轴0）</small>|
|<small>hstack</small>|<small>以面向行的方式对数组进行堆叠（沿轴1）</small>|
|<small>column_stack</small>|<small>类似于hstack，但是会先将一维数组转换为二维列向量。</small>|
|<small>split</small>|<small>沿指定轴在指定的位置拆分数组</small>|

---
# 高级应用
**数组的合并和拆分**
|函数|说明|
|:--|:--|
|<small>hsplit, vsplit, dsplit</small>|<small>split的便捷化函数，分别沿着轴0、轴1和轴2进行拆分。</small>|

- _r和_c对象: 简化堆叠代码编写
- 例子代码: <small>advanced_array_manipulation/concatenating_and_splitting_arrays.py</small>

---
# 高级应用
**元素的重复操作**
- tile
- repeat
- 例子代码: <small>advanced_array_manipulation/repeating_elements.py</small>

---
# 高级应用
**花式索引的等价函数**
- take
- put
- 例子代码: <small>advanced_array_manipulation/fancy_indexing_equivalents.py</small>