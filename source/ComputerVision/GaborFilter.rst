 图像分析：Gabor滤波器解析与编程
==================================


为了研究局部范围内的频域特性，Gabor 提出短时傅里叶变换，也就是Gabor变换，
*实质上是一种高斯窗的fourier 变换，显示不同频率不同方向的信息。*  

其频域响应为：

.. math::

   H\left( {u,v} \right) = 2\pi {\delta _x}{\delta _y}\left[ {{e^{ - 2{\pi ^2}\left[ {{{\left( {\mu  - {\mu _0}} \right)}^2}\delta _x^2 + {{\left( {v - {v_0}} \right)}^2}\delta _y^2} \right]}}} \right]

从其频域形式可以看出，其等同于移动从原点高斯函数到
:math:`(\mu_0,v_0)` ，因此Gabor 滤波器可以看作从原点移动函数 :math:`\sqrt((\mu_0)^2+(v_0)^2)` ,并且按照方向 :math:`tan^{-1}\frac{\mu_0}{v_0}`, 参数 :math:`(\sigma_x,\sigma_y)` 用来确定滤波器带宽。注意变量写的不太一致，具体参考：`Gabor Filters <http://www.cs.utah.edu/~arul/report/node13.html>`_ 。 

1985年Daugman扩展了Gabor滤波器的二维形式：

.. math::

   h\left( {x,y,{\theta _k},\lambda ,{\sigma _x},{\sigma _y}} \right) = \frac{1}{{2\pi {\sigma _x}{\sigma _y}}}\exp \left\{ { - \pi \left[ {{{\left( {\frac{{{x_{{\theta _k}}}}}{{{\sigma _x}}}} \right)}^2} + {{\left( {\frac{{{y_{{\theta _k}}}}}{{{\sigma _y}}}} \right)}^2}} \right]} \right\} \cdot \exp \left( {\frac{{2\pi i{x_{{\theta _k}}}}}{\lambda }} \right)


从上式中看出，Gabor是一个被复正弦函数调制的Gaussian函数，其中 :math:`\lambda` 和 :math:`\theta k` 分别是正弦波的波长和方向， :math:`\theta_ k` 的定义为：

.. math::

   {\theta _k} = \frac{\pi }{n}\left( {k - 1} \right), k = 1,2,....,n


k决定了滤波器方向的个数；
:math:`\sigma_x`  and  :math:`\sigma_y` 为高斯包络在x方向和y方向的标准差。

.. math::

   \left\{ \begin{array}{l}
   {x_{{\theta _k}}} =  + x\cos \left( {{\theta _k}} \right) + y\sin \left( {{\theta _k}} \right)\\
   {y_{{\theta _k}}} =  - x\cos \left( {{\theta _k}} \right) + y\sin \left( {{\theta _k}} \right)
   \end{array} \right.


Lee提出利用gabor滤波器呈现图像。Gabor滤波器是椭圆高斯包络和复平面波的乘积，可以表示为：

.. math::

   \begin{array}{c}
   {\Psi _{s,d}}\left( {x,y} \right) = {\Psi _{\vec k}}\left( {\vec z} \right) = \frac{{||\vec k||}}{{{\delta ^2}}} \cdot \exp \left( { - \frac{{||\vec k|{|^      2} \cdot ||\vec z|{|^2}}}{{2{\delta ^2}}}} \right)\\
    \times \left[ {\exp  i\vec k \cdot \vec z - \exp \left( { - \frac{{{\delta ^2}}}{2}} \right)} \right]
   \end{array}

其中 :math:`\vec z=[x,y]` 是空域变量，
:math:`\vec k` 是频域变量，用来确定Gabor 滤波器的尺度和方向， :math:`\vec k = {k_s}{e^{i{\phi _d}}}`.

详细参考：

#. http://blog.csdn.net/linj_m/article/details/9897439
