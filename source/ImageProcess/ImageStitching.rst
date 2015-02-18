图像拼接
********

Lucas–Kanade 方法 
======================

图像拼接最重要的是在找到匹配对之后，求转换矩阵。L-K算法通过目标函数是
.. math:: {\sum\limits_{{\rm{patch}}} {\left[ {I\left( {W\left( {X;p} \right)} \right) - T\left( x \right)} \right]} ^2}，通过对次公式进行泰勒展开，
并对信号进行求进行链式求导：


.. math:: \frac{{\partial I}}{{\partial p}} = \frac{{\partial I}}{{\partial W}}\frac{{\partial W}}{{\partial p}}{\rm{ = }}\left\langle {\nabla I,\left[ {\frac{{\partial {W_x}}}{{\partial p}}\frac{{\partial {W_y}}}{{\partial p}}} \right]} \right\rangle 
最后用最小二乘算法实现对p的估计。

See also
========

#. `一种基于区域匹配的图像拼接算法 <http://wenku.baidu.com/view/3f5488c42cc58bd63186bd3a.html>`_  
#. `图像拼接算法及实现 <http://wenku.baidu.com/view/36fc73c30c22590102029df8.html>`_  拼接算法主要两类一类是分域匹配，另一个基于特征提取
#. `图像拼接Image Mosaic <http://www.legalsoft.com.cn/image-mosaic/>`_  北京联高软件开发有限公司


