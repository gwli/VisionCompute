+`OpenCV 学习笔记（四十六）——FAST特征点检测features2D <http://blog.csdn.net/yang_xian521/article/details/7411438>`_ 
======================================================================================================================================
.. math::

N = \sum\limits_{x\forall \left( {circle\left( p \right)} \right)} {|I\left( x \right) - I\left( p \right)|}  > {\varepsilon _d}

其中I（x）为圆周上任意一点的灰度，I （p）为圆心的灰度，Ed为灰度值差得阈值，如果N大于一定的阀值，则认为p是一个特征点。
