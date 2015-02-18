+本节参考：RANSAC for Dummies.pdf
======================================

RANSAC包含两个步骤，首先是在Hypothesize随机假设一个数据集（MSSs），然后，计算参数，然后在test步骤排除这些不可靠的参数。

假设原来有N个数据集 :math:`D={d_1,...,d_N}` , :math:`\theta({d_1,...,d_N})` 是使用数据集:math:`D={d_1,...,d_N}`, 要估计的参数，其中，:math:`h\geq k` ，其中k是基数线。因此模型M可以表示为：

.. math::

   M\left( \theta  \right) = { {d \in {\Re^d}:{f_M}( {d;\theta }) = 0} }

其中 :math:`f_M` 是平滑函数，它的零水平集包含所有满足模型M的参数 :math:`\theta`. 定义数据d和模型:math:`M(\theta)` 之间的误差为：

.. math::

   e\left( {d,M\left( \theta  \right)} \right) = \mathop {\min }\limits_{d\prime \in M\left( \theta  \right)}  dist\left( {d,d\prime} \right)


使用这个误差标准，一致集定义为：

.. math::

   S\left( \theta  \right) = \left\{ {d \in D:e\left( {d,M\left( \theta  \right)} \right) \le \delta } \right\}


其中误差函数写为：

.. math::

   e\left( {d,M\left( \theta  \right)} \right){\rm{ = }}\mathop {\min }\limits_{d \in M\left( \theta  \right)}  \sqrt {\sum\limits_{i = 1}^n {{{\left( {{d_i} - {d_i}} \right)}^2}} }  = \sqrt {\sum\limits_{i = 1}^n {{{\left( {{d_i} - d_i^*} \right)}^2}} } 


其中 :math:`d^*` 是d在 :math:`M(\theta)` 上的投影。假设数据d是由于高斯噪声产生的:math:`\eta\sim\aleph(0,\sigma_{\eta} I)`, 因此 :math:`\eta=d-d^{\star}`, 我们的目标是是要计算数值:math:`\delta`,使得给定概率:math:`P_inlier`.

.. math::

   P[e(d,M(\theta))\leq=P_{inlier}]


根据概率密度函数，我们可以得到如下公式：


.. math::

   P[e(d,M(\theta))\leq\delta]=P[\sum_{i=1}^n \eta_i^2\leq\delta^2]=P[\sum_{i=1}^n (\frac{\eta_i}{\delta_{\eta}})^2\leq{\frac{\delta}{\sigma_{\eta}}}^2]


因为
:math:`\eta_i/\sigma_{\eta}\sim\aleph(0,1)` ,随机 :math:`\sum_{i=1}^{n}(\frac{\eta_i}{\sigma_{\eta}})^2 服从:math:`\chi_n^2分布，因此： 

.. math::

   \delta {\rm{ = }}{\sigma _\eta }\sqrt {F_{\chi _n^2}^{ - 1}\left( {{P_{inlier}}} \right)} 


+需要多少次重复？？
============================

假设q是从数据集D中采样一个准确的MSSs的概率，那么至少有一个错误的参数为1-q。如果构建h个不同的MSSs，那么被outlier污染的概率为 :math:`(1-q)^h` , 我们期望 :math:`(1-q)^h` 小于等于门限:math:`\varepsilon`,也就是:math:`(1-q)^h\leq \varepsilon`,上述关系可以写作为：

.. math::

   h \ge \left\lceil {\frac{{\log \varepsilon }}{{\log \left( {1 - q} \right)}}} \right\rceil 


+计算MSSs并且计算q
========================

如果数据集D中的所有数据都是没有噪声的，那么那么获得一个稳定的MSSs，只有inliers的概率为：

.. math::

   q = \frac{{\left( \begin{array}{l} {N_I}\\
   k \end{array} \right)}}{{\left( \begin{array}{l} N\\
   k \end{array} \right)}} = \frac{{{N_I}!\left( {N - k} \right)!}}{{N!\left( {{N_I} - k} \right)!}} =\prod_{i=0}^{k-1}(\frac{{{N_I} - i}}{{N - i}})

其中 :math:`N_I` 是inliners个数。如果 :math:`N,{N_I} \gg k` 公式可写为：

.. math::

   q = \prod\limits_{i = 0}^{k - 1} {(\frac{{{N_I} - i}}{{N - i}})}  \approx {\left( {\frac{{{N_I}}}{N}} \right)^k}


但是实际中选取的inliers 总是满足： :math:`\hat N_I\leq N_I` ,因此有 :math:`q(\hat N_I)\leq q(N_I)`, 最后有:math:`{\left( {1 - q\left( {{N_I}} \right)} \right)^h} \ge {\left( {1 - q\left( {{{\hat N}_I}} \right)} \right)^h}`,从而有重复次数更新为：

.. math::

   {{\hat T}_{iter}} = \left\lceil {\frac{{\log \varepsilon }}{{\log \left( {1 - q\left( {\hat N} \right)} \right)}}} \right\rceil 


*后期就是按照EM算法实现*


#. 首先对任意选取的h个参数，然后估计参数模型。

#. 找到参数模型时，重新调整inlier和outlier选取的点，重新估计参数。

#. 重复上述步骤，直达算法中种子点没有移动，也就是达到稳定状态。
   
   具体参考`K-means <Study.MachineLearningAndImageDetect>`_ 算法。

-+`随机抽样一致性算法（RANSAC) <http://www.cnblogs.com/xrwang/archive/2011/03/09/ransac-1.html>`_ 
============================================================================================================

Ransac 从一组包含局外点的观测数据中，通过迭代的方式估计数学模型的参数，w表示从所有点中，每次选择局内点的概率,p表示迭代过程中随机选取出的点均为局内点的概率，因此P表征了算法产生有用结果的概率。

假设估计模型需要选定n个点， :math:`w^n`  是所有n点均为局内点的概率； :math:`1-w^n` 是n个点中至少有一个是局外点的概率，此时表示我们评估了一个不好的模型。:math:`(1-w^n)^k` 表示算法永远都不会选择到n个点均为局内点的概率，它和1-p相同，因此：

.. math::

   1-p=(1-w^n)^k

对上式两边取对数，得到：

.. math::

   k = \frac{{\log \left( {1 - p} \right)}}{{\log \left( {1 - {w^n}} \right)}}


值得注意的是，这个结果是假设n个点都是独立选择的。为了得到更可信的参数，标准偏差或者它的乘积被加到k上。k的标准偏差定义为：

.. math::

   SD\left( k \right) = \frac{{\sqrt {1 - {w^n}} }}{{{w^n}}}

