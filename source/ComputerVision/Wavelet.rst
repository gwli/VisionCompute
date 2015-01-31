Introduction
============

   小波变换区别于傅里叶变换的主要原因就是 小波变换没有特定的basis，他是根据母小波和父小波（scale function）来逐步递归确定的，因此他比较适合于有突变的地方，其中wavelet function 提供了一个多尺度分析，我想和金字塔信号，就是提供了一个伸缩函数，可以灵活的想要的分辨率。

* `Image Denoising with Wavelets <https://www.ceremade.dauphine.fr/~peyre/numerical-tour/tours/denoisingwav&#95;2&#95;wavelet&#95;2d/>`_  小波降噪 matlab版本的
#. `小波变换PPT <http://wenku.baidu.com/view/dcae2730ee06eff9aef8076a.html>`_  有限长均值为0的函数都为小波函数，能量集中。再看那个差值的分布，例均值，放在左与上，差值放在右与下，这样不就形成多分辨率了，只要从左上到右下逐步取值不就形了。可以直接计算出来当前图像的大小。这样的多尺度变换与MIPMAP 的存储关系。
#. `小波变换 完美通俗解读 <http://blog.sina.com.cn/s/blog&#95;5d942c720100q6sd.html>`_  正线性的空间的基与向量的最大无关组，利用最大无关组来表示其他向量。系数的个数与最大无关组的个数，那么图像我们能不能每一行当做一个向量组，然后求出最大无关组。这样不是可以压缩数据了。一般对于图像的压缩都是采用分块的模式。 `amsci <http://www-math.mit.edu/~gs/papers/amsci.pdf>`_  从这一篇文章中我们可以看从向量的无关组来延伸出来的，Haar矩阵。`wavelet in wikipedia <http://en.wikipedia.org/wiki/Wavelet>`_ 
  如何利用矩阵的初等变换与求矩阵的逆。



小波在图像中应用
========================

残差计算，子带编码，哈尔变换。
对于图像的压缩编码，应该有逐级变换解码的算法。每一点的值，应该是有固定的路径。而不必须每一次都把全部的运算解开。%RED%可以利用这种方法来产生一个算法性texture,再加分型的应用。 %ENDCOLOR%




Hilbert 和wavelet 变换的关系

-- Main.GegeZhang - 16 Aug 2013


傅里叶变换中的基也应该是正交的

-- Main.GegeZhang - 16 Aug 2013


尺度函数（父小波）：对自己本身周期平移的函数两两正交，为什么

-- Main.GegeZhang - 16 Aug 2013


*稀疏矩阵*
小波变换其实有点类似于稀疏矩阵。特别是适合于，一个主波在不同的段有不同的波形组成。

-- Main.GangweiLi - 15 Sep 2013


*哈尔变换*
是基固定，只是用来求系数。因为只有加减运算速度很快。

-- Main.GangweiLi - 15 Sep 2013


*JPEG*
1. DCT 计算
1. 量化
1. 变长编码
图像分成8x8的像素块来进行的。

-- Main.GangweiLi - 15 Sep 2013


http://glearning.tju.edu.cn/course/view.php?id=677

-- Main.GegeZhang - 23 Sep 2013
