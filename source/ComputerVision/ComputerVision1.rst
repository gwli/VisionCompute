RANSAC包含两个步骤，首先是在Hypothesize随机假设一个数据集（MSSs），然后，计算参数，然后在test步骤排除这些不可靠的参数。

假设原来有N个数据集 :math:`D={d_1,...,d_N}` ,  :math:`\theta({d_1,...,d_N})` 是使用数据集 :math:`D={d_1,...,d_N}`, 要估计的参数，其中， :math:`h\geq k` ，其中k是基数线。因此模型M可以表示为：


.. math::

   M\left( \theta  \right) \triangleq { {d \in {^d}:{f_M}( {d;\theta }) = 0} }


其中
:math:`f_M` 是平滑函数，它的零水平集包含所有满足模型M的参数 :math:`\theta` . 定义数据d和模型 :math:`M(\theta)` 之间的误差为：

.. math::

   e\left( {d,M\left( \theta  \right)} \right) = \mathop {\min }\limits_{d\prime \in M\left( \theta  \right)}  dist\left( {d,d\prime} \right)


使用这个误差标准，一致集定义为：

.. math::

   S\left( \theta  \right) = \left\{ {d \in D:e\left( {d,M\left( \theta  \right)} \right) \le \delta } \right\}


其中误差函数写为：

.. math::

   e\left( {d,M\left( \theta  \right)} \right){\rm{ = }}\mathop {\min }\limits_{d \in M\left( \theta  \right)}  \sqrt {\sum\limits_{i = 1}^n {{{\left( {{d_i} - {d_i}} \right)}^2}} }  = \sqrt {\sum\limits_{i = 1}^n {{{\left( {{d_i} - d_i^*} \right)}^2}} } 


其中
:math:`d^*` 是d在 :math:`M(\theta)` 上的投影。假设数据d是由于高斯噪声产生的 :math:`\eta\sim\aleph(0,\sigma\eta I)` , 因此  :math:`\eta=d-d\star`, 我们的目标是要计算数值:math:`\delta`,使得给定概率:math:`P_inlier`.
