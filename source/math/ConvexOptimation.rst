优化理论
***********

梯度优化方法
-------------

梯度下降法原理：梯度方向是沿着曲线上升变化最快的，因此对于最小化问题，使用负梯度方向则能够找到最优点。怎样保证这一步和下一步的梯度是正交的。但是具体怎样推倒：

首先函数式利用泰勒展开式，

我们对于最小值问题，n维空间的一个点移动到另一点之后，目标函数的改变情况，因此写出代表最终的目标函数的数学表达式:

.. math::

   f(x_k+ad) = f(x_k)+\alpha g_k^Td + O(\alpha)

其中 :math:`x_k` 代表第k个点的自变量（一个向量）。d是一个单位向量，即|d|=1.
:math:`\alpha` 是步长， :math:`g_k^T` 表示目标函数在 :math:`x_k` 这一点的梯度。

在上式中要使得（1）式样取得最小，应使 :math:`g_k^T d` 取得最小，因此只有也就是d取 :math:`-g_k` 时，下降速度最快，这就是最速下降法的由来。

http://www.codelast.com/?p=2573



牛顿迭代公式
---------------

根据泰勒公式，在 :math:`x_0` 处一阶展开，得到：

.. math::
   f(x)=f(x_0)+(x-x_0)f^{\prime} (x_0)

求解方程f(x)=0,即 :math:`f(x_0)+(x-x_0)*f^{\prime}(x_0)=0`,求解得到：

.. math::
   x =x_1=x_0-f(x_0)/f\prime(x_0)

.. note::
   从这个看出，后一个位置的x可以由前一个位置的x_0迭代而产生，于是迭代的想法就自然了。

进而可以推导出:

.. math::

   x(n+1)=x(n)-f(x(n))/{f^\prime (x(n))}

（这里的和最终的梯度下降法怎样推倒？）
通过这个式子，得到这个式子在 :math:`(x\star)=0` 的时候收敛，整个过程如下：


   
.. figure:: images/gradient.jpg
    :width: 400px
    :align: center
    :height: 200px
    :alt: alternate text
    :figclass: align-center

     梯度下降法求实根示意图
 


牛顿法：

.. math::

   \theta_{i + 1}} = \theta_i - \alpha {J_i}/\nabla{J_i} 
   
相比梯度下降法速度更快。 然后又将了GLM，说明最小二乘和 logistic 回归都是GLM 指数分布的特殊情况。是不是我们现在的所有问题都是指数分布？主要是通过把某个问题划归为某个分布，然后求出期望:math:`\mu` ，从而得到h(x)函数。


牛顿法：

把式子写为二阶形式，得到：

.. math::

   f(x+\bigtriangleup) =f(x)+f\prime \bigtriangleup x+\frac{1}{2}f^{\prime\prime}\bigtriangleupx^2

这个式子是成立的，当且仅当 :math:`\bigtriangleup x` 无限地趋近于0，此时上式等价于：

.. math::

   f\prime(x)+f^{\prime\prime}\bigtriangleup x =0

   （这个式子是怎样得到的？）
求解得到：

.. math::
   
   \bigtriangleup x = -\frac{f^\prime(x_n)}{f^{\prime\prime}(x_n)}

得到迭代公式：

.. math::

   x_{n+1} = x_n -\frac{f^\prime(x_n)}{f^{\prime\prime}(x_n)}

一般认为牛顿法可以利用到曲线本身的信息，比梯度下降法更容易收敛（迭代更少次数），如下图是一个最小化一个目标方程的例子，红色曲线是利用牛顿法迭代求解，绿色曲线是利用梯度下降法求解。

   
.. figure:: images/NewtonMethod.jpg
    :width: 400px
    :align: center<F5><F5><F5><F5><F5>
    :height: 200px
    :alt: alternate text
    :figclass: align-center

     梯度下降法求实根示意图

从这个角度来讲，梯度下降法，只使用一阶信息，相当于使用基于平面的优化，而牛顿法使用二阶信息，相当于基于曲面的优化。 

最优化问题中，牛顿法为什么比梯度下降法求解需要的迭代次数更少？ http://www.zhihu.com/question/19723347
