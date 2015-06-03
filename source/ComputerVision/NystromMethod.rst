谱聚类算法
**************


Nystrom method
===============

求数据集之间的相似度矩阵，构造成相似度图，然后求得某种形式的Laplacian Matrix,然后求得Laplacian matrix的前k个特征向量，随后k个特征向量组成的矩阵U的前K个行向量作为输入，运行K-means 算法，得到最后的聚类结果。这要求对整个整数集进行处理，在很多应中是不符合的。可用于当数据规模巨大时运行谱聚类算法的场景。

Nystrom Method 用于求解如下形式的积分方程：

.. math::
   \int_a^b W(x,y)\phi(y)dy = \lambda \phi(x)

在[a,b]中间取n个均分点，并用矩阵公式将积分写成数值计算形式：

.. math::

   \frac{b-a}{n}\sum_{j=1}^n W(\xi_i,\xi_j)\hat\phi(\xi_j) =\lambda(\hat\phi\xi_i) \existsi \in {1,...,n}

特殊地，令[a,b]为[0,1], 上式表示成矩阵形式： :math:`A\hat\Phi`=n\hat\Phi`\Lambda. 于是得到 Nystrom Extension公式：

.. math::

   \hat\Phi_i(x)= \frac{1}{n\lambda}\sum_{j=1}^nW(x,\xi_j)\hat\phi_i(\xi_j)


 这个公式表明矩阵分解可以表示成矩阵分解形式。

http://blog.sciencenet.cn/blog-799581-626691.html
