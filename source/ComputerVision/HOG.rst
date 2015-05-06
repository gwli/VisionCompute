HOG特征
=========

HOG的核心思想是所检测的物体外形能够被光强梯度或边缘方向的分布所描述。通过将一副图像分解成小的连接区域（称为cells），每个cell生成一个方向梯度直方图或者cell中的pixel的边缘方向，这些直方图的组合可以表述为描述子。为改善准确率，局部直方图可以通过计算图像中的一个较大区域（称为Block），为measure被对比标准化，然后这个值（measure）归一化这个block中的所有cells. 这个归一化过程实现了阴影不变性。

HOG过程
--------

#. 灰度化
划分成小的cells
计算每个pixel的gradient（即orientation）
统计每个cell的梯度直方图（不同梯度的个数），即每个cell的descriptor。
