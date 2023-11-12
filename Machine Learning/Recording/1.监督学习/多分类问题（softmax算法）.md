# **多分类问题**（softmax算法）

 概述：将问题依据给定的有限个离散的标签进行分类

## 1.SoftMax回归

定义：
	如标签y可以取：1~N；
	$z_j = \vec{w_j}\vec{x} +b_j $   (j = 1,2,3,……,N)
	参数（parameters）:$w_1,w_2,w_3,,\cdots,w_N  ~~~~~~~b_1,b_2,b_2\cdots b_j$ 
	$a_j = \frac{e^{z_j}}{\sum\limits_{k= 1}^{N} e^{z_k}}$  (y = j|x，这表示y的取值是x中的第j个)
	$a_1+a_2+a_3+\cdots+a_n = 1$

#### 损失函数

$a_1 = \frac{e^{z_1}}{e^{z_1}+e^{z_2}+\cdots+e^{z_N}}$  (P(y = 1 | X))
$\vdots$
$a_N = \frac{e^{z_N}}{e^{z_1}+e^{z_2}+\cdots+e^{z_N}}$   (P(y = N | X))



$$loss(a_1,\cdots,a_N,y) = \left\{ \begin{array}{**lr**}
	-\log{a_1} ~~~~~ if~y = 1 ,& \\
	-log(a_2) ~~~~ if~y = 2,& \\
	\vdots &\\
	-log{a_N} ~~~~ if~ y = N &  \end{array}\right.  $$  



$loss = -\log{a_j}~~~~if~y = j$      该损失函数称为：交叉熵损失，$a_j$ 相当于是预测正确的概率，当 $a_j$ = 1时，L = 0，说明完全预测正确，且此时的损失为0。

softmax的输出（$a_1,\cdots,a_n$）表征了不同类别之间的相对概率，对于输入$\vec{X}$ ，得到结果$a_1,a_2,a_3,\cdots,a_N$ ，看哪个值大，就认为分到了哪一类。
