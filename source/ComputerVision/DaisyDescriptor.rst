Daisy 算子

参考文献：DAISY: An Efficient Dense Descriptor Applied
to Wide-Baseline Stereo

这个算法利用多层高斯卷积核进行计算：

对于任给一方向o,该方向的方向图定义为：

%\[G_o=(\frac{\partial I}{\partial o})^+\]%

其中操作
.. math:: (.)^+$%表示%$(a)^+=max(a,0) 这个约束是保证梯度方向不改变。

分别将这些不同方向图与一系列具有不同卷积核的高斯函数做卷积，生成不同的尺度图：

%\[G_o^\Sigma=G_{Sigma}*(\frac{\partial I}{\partial o})\]%

这些尺度图用于后续的特征向量的计算。

%\[h_{Sigma}(l_j(u,v,R_i))=[G_1^{\Sigma}(l_j(u,v,R_i)),...,G_H^{\Sigma}(l_j(u,v,R_i))]\]%

#. `Daisy 步骤 <http://www.cs.ubc.ca/>`_  

