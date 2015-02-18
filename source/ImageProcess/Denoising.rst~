图像降噪
********

k-L 变换就是求数据的协方差矩阵的特征值和特征向量。

-基于PCA的降噪，
======================

PCA降噪方法和之前的降维差不多，对于降噪来说，就是获得信号子空间和噪声子空间，-》从噪声子空间中估计噪声方差-》remove 噪声子空间

小波变换
============

haar变换，就是利用上一个点对下一点进行相减，在信号不变的情况下，得到的信号就是稀疏的，稀疏之后然后在通过设置门限就可以把噪声抑制掉。

`量子成像 <Quantum Imaging>`_ 

相干斑
=========

相干斑主要是相干成像中明暗变化的图像，产生主要是由于单个距离分辨单元中包含多个目标，结果多个信号相加生成随机的信号幅度和相位，主要抑制相干斑的方法

#. 基于multi-looking processing， 但是这样会降低雷达的分辨力（好像是方位分辨率吧）
#.  基于小波变换的方法。
#.  基于ICA的方法。
#. 基于自适应滤波的方法。

#. `k-L变换 清华 <http://media.cs.tsinghua.edu.cn/~ahz/digitalimageprocess/chapter11/chapt11&#95;ahz.htm>`_  
#. `k-L变换，里面还有一些基本的主分量分析，小波变换等的数学推导 <http://fourier.eng.hmc.edu/e161/lectures/klt/node3.html>`_  
#. `adesso  <http://parati.dca.fee.unicamp.br/adesso/wiki/>`_  Adessowiki - Collaborative Scientific Writing and Programming
#. `klt找到脸位置，matlab代码 <http://www.mathworks.cn/cn/help/vision/examples/face-detection-and-tracking-using-the-klt-algorithm.html>`_  
#. `scikit-learn: machine learning in Python <http://scikit-learn.org/0.13/modules/classes.html>`_  有空看一下
#. `PCA降噪matlab代码 <http://www4.comp.polyu.edu.hk/~cslzhang/LPG-PCA-denoising.htm>`_  
#. `PCA降噪python 代码 <http://scikit-learn.org/0.13/auto&#95;examples/decomposition/plot&#95;kernel&#95;pca.html>`_  怎样装上他们开发的modulate
#. `自适应变换小波降噪 <http://www.google.com.hk/url?sa&#61;t&#38;rct&#61;j&#38;q&#61;data-adaptive&#37;20transforms&#38;source&#61;web&#38;cd&#61;1&#38;ved&#61;0CC4QFjAA&#38;url&#61;http&#37;3a&#37;2f&#37;2fwww&#37;2espringer&#37;2ecom&#37;2fcda&#37;2fcontent&#37;2fdocument&#37;2fcda&#95;downloaddocument&#37;2f9788132209690-c2&#37;2epdf&#37;3fSGWID&#37;3d0-0-45-1355475-p174690988&#38;ei&#61;tpAAUt2wAsfolAXanIBI&#38;usg&#61;AFQjCNGM001r6M45XninKtmLFWIN9-aoSg&#38;bvm&#61;bv.50310824,d.dGI&#38;cad&#61;rjt>`_  
#. `多分辨率curvelet transform <http://authors.library.caltech.edu/6810/2/CANmms06preprint.pdf>`_  
#. `wavelet.py 图像小波降噪 <http://www.google.com.hk/url?sa&#61;t&#38;rct&#61;j&#38;q&#61;wavelet.py&#37;20&#37;20import&#37;20pywt&#37;20import&#37;20Image&#37;20&#37;20denoise&#38;source&#61;web&#38;cd&#61;1&#38;ved&#61;0CCkQFjAA&#38;url&#61;https&#37;3a&#37;2f&#37;2fgist&#37;2egithub&#37;2ecom&#37;2fsynnick&#37;2f5644377&#38;ei&#61;P7QAUq7eIsbUkQWKn4HgDw&#38;usg&#61;AFQjCNGP3OdZyUrZ-54EnYi3tH3nRj49zg&#38;bvm&#61;bv.50310824,d.dGI&#38;cad&#61;rjt>`_  

 * `specle降噪 <http://en.pudn.com/downloads126/sourcecode/math/detail534908&#95;en.html>`_  
#. `A beginner's guide to speckle <http://dukemil.bme.duke.edu/Ultrasound/k-space/node5.html>`_  
#. `合成孔径雷达基础 <http://www.radartutorial.eu/20.airborne/ab07.en.html>`_  
#. `相干斑形成原理 <http://wenku.baidu.com/view/6927221014791711cc79173e.html>`_  这个基本还行，理解了相干斑 
#. `Lee滤波，这个是python 版本的，但是这个看不太懂，让老李看下 <https://github.com/josephmeiring/LeeFilter>`_  
#. `量子力学 <http://open.sina.com.cn/course/id&#95;32/>`_  

降噪首先分为两种方法：第一种是目标信号增强，增强信噪比，另一种是降低噪声

-- Main.GegeZhang - 03 Aug 2013


微弱小目标降噪 方法 k-l transform, wavelet, correlation analysis

-- Main.GegeZhang - 04 Aug 2013


动态背景建模方法

-- Main.GegeZhang - 04 Aug 2013


为什么在K-L变换中首先要减去平均值，是噪声吗？

我想是噪声，其实方差矩阵就是数据的抖动.

-- Main.GegeZhang - 04 Aug 2013


小波变换 视频

-- Main.GegeZhang - 06 Aug 2013


小波变换可以降噪？

-- Main.GegeZhang - 06 Aug 2013


svd 分解在特征值之后最小的特征值有均匀分布的特点，可以通过特征值来识别，那特征值是最好的吗？ 对于噪声？ 还有哪些？

-- Main.GegeZhang - 06 Aug 2013


PCA只适用于高斯噪声？

-- Main.GegeZhang - 06 Aug 2013


对于对GPS的导航，船，我们应该怎么办？设计更好的信号？怎么设计？

-- Main.GegeZhang - 06 Aug 2013


小波变换傅里叶变换的区别和联系

-- Main.GegeZhang - 06 Aug 2013


`data-adaptive transforms'.有空看一下，是不是可以获得更好的结果，相比傅里叶变换和小波变换

-- Main.GegeZhang - 06 Aug 2013


curvelet transform,是什么　多分辨率的，具体是什么

-- Main.GegeZhang - 06 Aug 2013


稀疏的，和降噪是一体的，目的就是获得更少的数据

-- Main.GegeZhang - 06 Aug 2013


就像手机铃声一样，这样应用虽然没有什么技术含量，但是使用的人却是非常多，比如让人很容易的表现出自己的个性，想qq空间中的，人可以上传自己的图片，可以加入评语，

-- Main.GegeZhang - 06 Aug 2013


为什么2的整数次幂，计算机容易实现？

-- Main.GegeZhang - 06 Aug 2013


我想相干斑 也可以用 盲源分离来抑制

-- Main.GegeZhang - 13 Aug 2013


对于纪晨华中的问题是不是也会出现一个分辨单元中多个信号，分辨率不够，

如果对于一个照射源的话，还有这个问题吗？

-- Main.GegeZhang - 13 Aug 2013


 Rayleigh 和  Rician分布的区别，  Rician 应该是Rayleigh加一个强信号就可以了吗

-- Main.GegeZhang - 13 Aug 2013


纪晨华的问题我想可不可以成像？ 是可以在信号上处理也可以在图像上处理

-- Main.GegeZhang - 13 Aug 2013


什么是循环高斯过程？

-- Main.GegeZhang - 13 Aug 2013


对于乘性噪声，可以通过同态滤波器，转换为同态滤波器，这样基于加性噪声的滤波器就可以用来降噪了

-- Main.GegeZhang - 13 Aug 2013


在雷达目标探测和成像上，有什么区别和类似？吴博士

-- Main.GegeZhang - 13 Aug 2013


zero-mean什么

-- Main.GegeZhang - 13 Aug 2013


 k-space dimension 什么

-- Main.GegeZhang - 13 Aug 2013


为什么谱白化会加强热噪声效应？

-- Main.GegeZhang - 13 Aug 2013


小波降噪的程序，在噪声未知情况下 现在还没有找到

-- Main.GegeZhang - 19 Aug 2013


图像处理在信号上降噪的？也就是在图像之前？ 老刘都是假设信号是纯净的.

-- Main.GegeZhang - 19 Aug 2013
