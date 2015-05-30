级联算法
**************

随机森林

下述方法都是基于Bootstraping方法的计算，得到有放回的抽取：

bagging算法
-----------

训练样本集

.. math::
   S = {(X_1,Y_1),(X_2,Y_2),...,(X_n,Y_n)}

得到第i轮的训练函数

.. math::
   H(X)=f(\sum_{i=1^TH_i(X)})  

得到最终预测函数


Adaboost 分类器
---------------------

首先对N个训练样本的学习得到一个弱分类器
将分错的样本和其他数据一起构成新的N个的训练样本，得到第二个弱分类器。
继续进行。。。
将所有的分类器融合为一个强分类器。



这个算法思想就是每一次分类都是弱分类器，然后通过多次分类，最终形成一个强分类器。

算法具体步骤是：


#. 给定一定的训练集合，

.. math:: 
   (x_1,y_1),...,(x_m,y_m)$%,其中 %$x_i \in X, y_i\in Y=\{-1,1\}

#. 首先初始化分类器：

.. math:: D_1(i)=1/m

#. 训练弱分类器使用D_t分布。
#. 得到弱分布假设

.. math:: 

    h_t:X\rightarrow \{-1,1\},
    
得到误差：

.. math::

    \varepsilon=Pr_{i\sim D_t}[h_t(x_i)\neq y_i

#. 选择: :math:`\;{\alpha _t}{\rm{ = }}\frac{1}{2}ln(\frac{{1 - {\varepsilon _t}}}{{{\varepsilon _t}}})`

#. 更新：

.. math::

   \begin{array}{c}
   {D_{t + 1}}\left( i \right) = \frac{{{D_t}\left( i \right)}}{{{Z_t}}} \times \left\{ \begin{array}{l}
   {e^{ - {a_t}}}  {\rm{if}} {{\rm{h}}_t}\left( {{x_i}} \right){\rm{ = }}{y_i}\\
   {e^{{a_t}}}    {\rm{if}} {{\rm{h}}_t}\left( {{x_i}} \right) \ne {y_i}
   \end{array} \right.\\
    = \frac{{{D_t}\left( i \right)\exp \left( { - \;{\alpha _t}{y_i}{h_t}\left( {{x_i}} \right)} \right)}}{{{Z_t}}}
   \end{array}

#. 输出最后的假设：

.. math::`H\left( x \right) = sign\left( {\sum\limits_{t = 1}^T {{\alpha _t}{h_t}\left( x \right)} } \right)`

进一步的在人脸中的应用参考`Adaboost原理、算法以及应用 <http://www.zhizhihu.com/html/y2009/565.html>`_ 


`Adaboost 算法 <http://blog.csdn.net/haidao2009/article/details/7514787>`_ 

