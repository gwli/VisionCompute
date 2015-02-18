+`图像处理特征不变算子系列之SUSAN算子 <http://blog.csdn.net/kezunhai/article/details/11269793>`_ 
================================================================================================================


SUSAN算子通过一个圆形模板在图像上移动获得，模板内的每一个像素与中心像素进行比较：

.. math::

   c\left( {\vec r,{{\vec r}_0}} \right) = \left\{ \begin{array}{l}
   1      if|I\left( {\vec r} \right) - I\left( {{{\vec r}_0}} \right)| \le t\\
   0     if|I\left( {\vec r} \right) - I\left( {{{\vec r}_0}} \right)| > t
   \end{array} \right.


其中:math:`\vec r_0` 是中心像素，:math:`\vec r` 是掩膜内其它像素，t是一个像素差异阈值。

对上式进行统计，统计方式如下：

.. math::

   n(\vec r_0)=\sum_{\vec r}c(\vec r,\vec r_0)


得到的n值就是USAN的大小。

得到USAN值之后，通过阀值就可以得到初步的边缘响应，公式如下：

.. math::

   R({{\vec r}_0}) = \left\{ \begin{array}{l}
   g - n\left( {{{\vec r}_0}} \right)   if n\left( {{{\vec r}_0}} \right) < g\\
   0,  {\rm{otherwise}}
   \end{array} \right.


其中 :math:`g=3n_{max}/4`, USAN值越小，边缘的响应就越强，从而探测到边缘点。
