平滑空间滤波器
**************

特定滤波器（fspecial）：选择里面的平均滤波器
 一般多维滤波器（imfilter）作用：对感兴趣的物体得到一个粗略的描述而模糊小物体，较大物体变得像斑点而易于检测（为什么便于检测？）。
空间滤波器带来降噪的同时，也会产生图像模糊。

中值滤波器 （medfilt2）：降噪。

从空间滤波其中看到，blur使得图像最模糊，然后contour和FIND_EDGES中间正，两边负，可以得到图像的轮廓，
SMOOTH和SMOOTH_MORE平滑的越多图像越模糊。SHARPEN可以通过中间正，两边负的，得到图片增强。

图像逻辑运算（减法）
==============================

在matlab中图像是通过极坐标实现的，现在目前基于smile.jpg的结果是，从小到大变化图像半径和旋转角度，
半径 小->大，呈现图像的顺序嘴巴——》眼睛-》脸庞-》腮红。 这个出来的先后顺序是和这些边缘变化的模糊度有关，模糊度越高，出来的越慢。

旋转的作用那，现在看起来不是很明显。

空间滤波实现滤波 和目标分割 （基本原理：积分用来模糊图像，微分用来锐化图像）
=================================================================================================================


空域滤波，点检测，线检测

一阶算子方法：和可以实现对于明显的图像实现找到边界，
Sobel算子：内部利用局部平均方法，对噪声有一定的抑制作用。

Roberts算子： 检测边缘，对噪声敏感。（实际中使用什么检测特性还不清楚）

Prewitt算子：  采用局部平均，对噪声有一定的抑制作用。


二阶算子方法：能够更加清楚的找到边界，但是二阶算子对噪声比较敏感，因此首先的方法是首先进行平均降噪。


Laplace 算子： 具有各项同性微分算子，具有`旋转不变性 <http://www.narutoacm.com/archives/laplace-rotation-invariant/>`_ :

.. math::
   Laplace\left( f \right) = \frac{{{\partial ^2}f}}{{\partial {x^2}}} + \frac{{{\partial ^2}f}}{{\partial {y^2}}}

空域滤波，点检测，线检测。

频域滤波
============

DFT就像一个[[http://wenku.baidu.com/view/014797737fd5360cba1adbed.html[数学显微镜]]
频域滤波最终也要转换为空域处理。
#. `一个不错介绍 <http://homepages.inf.ed.ac.uk/rbf/HIPR2/fourier.htm>`_ 
 频域图能看出来什么，二维的频谱图与一维的有什么区别。从图像的频谱中能看到什么。变换前后的坐标与图有什么对应关系。进行卷积，进行子图识别，卷积最大的那个值，那就是图像重合的中心位置。时域的卷积等于频域的相乘。能否找到相关性最大的那个值。`子图的搜索也是基于此相关与卷积的 <http://blog.csdn.net/renshengrumenglibing/article/details/7066348>`_ . 这个时候先计算好两处图处DFT图，另外一个功能那就类似于积分图像的应用。

频域变化之后，的图像应该是三维的Sa函数。通过三维的高度来看比二维的颜色更加直观。并且可以取任意的细节利用带组，根据频域图的三维高度分度来进行提取。但是一个前提那就是你要知道图像中谁在哪一段频域上占着。想成一个三维的图，但是频域分布是圆周型，中心最低，越往边越高。就像水波纹一样。颜色越高说明系数越大。成分比较越大。并且频域与空域的点与点的距离是有对应的关系。

各种滤波器的设计，高通，低通，带通，完全可以利用图像来实现。频域的矩形滤波直接用阈值图像就可以搞定。渐变的频域图就像是曲线滤波了，例如巴特沃斯滤波器。等等。用在频域上试一试。那些数字滤器例如汉宁窗等等哪些能用到图像上。

一切都通了，频域的原点经过shift变在中间（M/2,N/2)。截止频率距离中间的距离，至于中间渐变颜色是根据滤波器来的，例如高斯。截止频率就是方差的大小。那期望如何来定呢。还是说只能是中心点的值。  现在要看看GIMP的渐变是如何实现，轴像与径向。是不是利用极坐标。然后按照函数值进赋值。

对于相关性与卷积，并且利用同样大小频域图来进行相乘。有一个周期截断的问题，那就需要扩展与截图了。

对于推导无非那些矩阵与求导的一些符号运算。积分，微分，卷积。矩阵的逆变换等等。这些基本知识。
#. `numpy.fft.fft2 <http://nullege.com/codes/search/numpy.fft.fft2>`_  这个库里一维，二维，多维，同时还可以提到一个序列采用频率。同时还有hfft,因为如果是纯实信号的FFT就是`hermitian transorm <http://en.wikipedia.org/wiki/Hermitian_function>`_ ，也是酉变换，也是正交变换。经过酉变换之后就都会变成对角阵。 在离散信号下的采用，其实我们平时序列的产生就是一种采样，例如,np.arange, np.linspace,np.logspace等等，包括你对序列直接进行的运算。所有对于序列的操作都可以看做是一种采样与滤波。
#. `斯坦福大学公开课：傅里叶变换及其应用 <http://v.163.com/movie/2008/2/6/6/M7Q4BLENR&#95;M7QBP2N66.html#>`_  
#. `图像的傅立叶变换 <http://www.cnblogs.com/xianglan/archive/2010/12/30/1922386.html#header>`_  傅里叶变换的形式。
   #. `fftw3-dev <http://www.fftw.org/>`_  GPL 库，并且支持 ARM NEON，作为以后移植方便。并且[[http://gfourier.sourceforge.net/ fftw 可以直接用到GIMP  GFourier]]
.. ::
  apt-get install fftw3-dev libgimp2.0-dev 
  同样小波变换也有类似插件。
#. `GIIMP PIL  <http://blog.csdn.net/liyong748/article/details/7554282>`_ 
#. `同态滤波论文去试一试 <http://wenku.baidu.com/view/1017d4212f60ddccda38a04c.html>`_ 
#. `图像渐变算法及实现 <http://staff.ustc.edu.cn/~lfdong/research/Biharmonic%20image%20warping.pdf>`_ 

See also
========

#. `图像的梯度 <http://hi.baidu.com/niiuniu1127/item/60d5acc8ecd2430dad092f89>`_  Sobel算子，不太明白
#. `python 简单图像处理（15） 图像的傅立叶变换 <http://www.cnblogs.com/xianglan/archive/2010/12/30/1922386.html>`_  
#. `拉普拉斯算子 <http://baike.baidu.com/view/1962085.htm>`_  
#. `梯度算子（普通的+Robert + sobel + Laplace） <http://blog.csdn.net/andkobe/article/details/5919733>`_  
#. `  拉普拉斯掩模锐化（1） <http://www.cnblogs.com/xfzhang/archive/2011/01/19/1939020.html>`_  
#. `图像处理：基础(模板、卷积运算)  <http://blog.csdn.net/xiaoxin&#95;ling/article/details/3587987>`_  
#. `图像处理中各种边缘检测的微分算子简单比较(Sobel，Robert， Prewitt，Laplacian，Canny) <http://blog.csdn.net/cay22/article/details/5591737>`_  
#. `Here is a collection of code fragments demonstrating some features of the OpenCV Python bindings. <http://opencv.willowgarage.com/documentation/python/cookbook.html>`_  Opencv手册，
#. `Roberts算子和Sobel算子的推导 <http://blog.csdn.net/quarryman/article/details/7408614>`_  
#. `图像处理常用边缘检测算子总结 <http://m.blog.csdn.net/blog/sangni007/8896542>`_  

#. `用博里叶频谱的偏振滤波作白光图像处理系统中的立体投影 <http://wenku.baidu.com/view/fc579937b90d6c85ec3ac648.html>`_  
#. `高斯图像滤波原理及其编程离散化实现方法 <http://blog.csdn.net/likezhaobin/article/details/6835049>`_  
#. `高斯滤波的sigma和mask之间的关系 <http://www.douban.com/note/252822401/>`_  基本知道了，根本为什么还不是很清楚


Thinking
========

拉普拉斯算子二阶导数增强细节，sobel算子边缘。

*一阶微分与二阶微分* http://blog.csdn.net/kayv/article/details/2261540
  1. 斜坡面上，一阶微分一直不为0 ；二阶微分只有终点和起点不为0
  1. 一阶微分产生较粗的边缘，二阶微分则细得多
  1. 一阶微分处理一般对灰度阶梯有较强的响应；二阶微分处理细节有较强的响应


对于小图像用mask不合适，因为会有模糊，那用什么方法合适那？mask尺寸和物体尺寸的关系。


怎样实现调用C代码？

*C:\快盘\graphic\paper\1673-2944(2012)03-0022-05.pdf*
基于DFT压缩。



如果我在较暗的情况下整体加上一个数的话，图像图像整体变量了，但还是对比度不高，


python 中怎样plt.axes 怎样调节参数



雷达数据 到成像 过程

-- Main.GegeZhang - 27 Jul 2013


雷达散射特性，前向散射，后向散射？什么联系，为什么在机场的时候前向比较明显，前向散射是比后向散射明显。

`雷达RCS曲线 <http://aircraftdesign.nuaa.edu.cn/lo/Notes/14.pdf>`_ 中可以看出来机头，机尾 和两边机翼都比较明显


*对一维到二维一直推广，其实是假定了，图像线性时不变系统。所以先算行或者例都是没有关系。这是由于线性系统自身性质决定的。

