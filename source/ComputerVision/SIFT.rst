+二级金字塔算法
======================


sift是比较普遍的方法，但属于重量级武器。虽然可以通过bow、hash等方法加速，但要效果好在实现的时候还是需要有不少小trick的。至于局部的形变和局部匹配，可以在sift上做一些小改进，但效果一般。

ps：你的问题大多集中于同源图像的比较，应该属于image copy detection的范畴，与一般检索中的图像相似性度量不太一样，你可以搜搜相关的文献

`DoG (Difference of Gaussian)角点检测 <http://blog.csdn.net/abcjennifer/article/details/7639488>`_ 

`SIFT 算法：DOG尺度空间生产 <http://www.cnblogs.com/JiePro/p/sift_1.html>`_ 

用两幅图像的在不同参数下的高斯滤波结果相减，得到DOg图。


A = Process(Im, 0.3, 0.4, x);

B = Process(Im, 0.6, 0.7, x);

a = getExtrema(A, B, C, thresh);


为什么那因为唯一能产生尺度空间的核高斯核，它有一个变尺度的高斯函数
.. math:: G(x,y,\sigma)$%与图像%$I(x,y)产生,即：


.. math:: L(x,y,\sigma)=G(x,y,\sigma)*I(x,y)

其中是二维高斯核函数，表示为：

.. math:: G(x,y,\sigma)=\frac{1}{2\pi\sigma^2}e^{-(x^2+y^2)/2\sigma^2}

SIFT 建议在可以通过LOG原则可以通过DOG来得到：


.. math:: D(x,y,\sigma)=(G(x,y,k\sigma)-G(x,y,\sigma))*I(x,y)=L(x,y,k\sigma)-L(x,y,sigma)

其中k为相邻尺度空间倍数的常数。

为什么要用DOG来检测特征点？

证明只有LOG才具有真正的尺度无关性。

而Mikolajczyk发现，只有用
.. math:: \sigma^2 才能得到更加稳定的图像特征，

通过热传导方程也可以理解DoG和
.. math:: \sigma^2\nabla^2 G的近似性。

%\[\partial G/\partial \sigma=\sigma^2\nabla^2 G\]%

对上式进行有限差分运算得到：

%\[\sigma\nabla^2 G=\partial G/\partial \sigma\approx (G(x,y,k\sigma)-G(x,y,\sigma))/(k\sigma-\sigma)\]%

因此：

%\[{\rm{DoG = G}}\left( {x,y,k\sigma } \right) \approx \frac{{G\left( {x,y,k\sigma } \right) - G\left( {x,y,\sigma } \right)}}{{k\sigma  - \sigma }}\]%

* `尺度空间理论和SIFT算法小结 <http://wenku.baidu.com/view/a9231c75a417866fb84a8e0b.html>`_  尺度空间不同高斯合如何确定，并且后边的特征向量还是不能明白
#. `SIFT算法详解及应用(课件) <http://wenku.baidu.com/view/87270d2c2af90242a895e52e.html>`_  算法基本明白，但是细节还不明白为什么要学分组内组间呢

*利用Laplace算子的原来，用DOG 实现，并用Hessian矩阵实现特征点的探测。*



