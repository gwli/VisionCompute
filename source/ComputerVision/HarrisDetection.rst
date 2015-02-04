`Harris角点检测 <http://blog.sina.com.cn/s/blog_c144a0e401019vqp.html>`_ 
============================================================================

Harris 角点检测算法：

首先利用能量公式来约束：


.. math:: E_{x,y}=\sum_{\mu,v}w_{\mu,v}[I_{\mu+x,v+y}-I_{\mu,v}]^2

然后写成微分的形式：


.. math:: E_{x,y}=\sum_{\mu,v}w_{\mu,v}[x\dot X+y\dot Y+O(x^2,y^2)]^2

这个公式写为矩阵形式：


.. math:: E_{x,y}=(x,y)M(x,y)^T

其中  :math:`M = \left[ {\begin{array}{*{20}{c}}
A&C\\
C&B
\end{array}} \right]` 

然后根据理想的两个导向矢量应该满足：

.. math::
   `E=\eta_1 \dot (\alpha+\beta)^2+\eta_2 \dot (\alpha-\beta)^2\\ =(\alpha \dot \beta)-\eta(\alpha+\beta)^2 ` 

因为 

.. math:: Tr(M)=\alpha+\beta=A+B


.. math:: Det(M)=\alpha \dot \beta=A \dot B-C^2

最后推导出来:

.. math:: E=Det(M)-k\dot Tr(M)

如果E比较小的话，说明这个是平坦区域，如果E<0,说明是边缘区域，如果E>0,则说明是一个角点区域。

`缺点: <http://blog.sina.com.cn/s/blog_89c722730101903k.html>`_ 


（1 ）该算法不具有尺度不变性；（2 ）该算法提取的角点是像素级的；（3 ）该算法检测时间不是很令人满意。


#. `局部图像特征描述概述 <http://www.zhizhihu.com/html/y2012/3950.html>`_  

怎样看完文献之后，再进行一步的思路整理?
很多东西还没有进行仿真实验。


我想看完之后可以对这些算子进行整理，进行仿真实验
