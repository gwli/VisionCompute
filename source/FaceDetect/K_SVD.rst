K-SVD
*******


这是k-svd，直接使用原图像。

K_SVD算法模型
=============

..math::

\min\limits{D,X}{||Y-DX||_F^2}\;  \;\;subject \;to \forall i, ||x_i||_0\leq T_0

这里的K是over-complete字典大小。

更新dictionary D
=================
因为D是一个矩阵，需要求的元素很多，所以这里采用每次只估计一个D_j，其他$j\neq k$不变，交替迭代的方法。

..math::

\begin{array}{l}
||Y-DX||_F^2=||Y-\sum_{j=1}^Kd_jx_T^j||_F^2\\
=||(Y-\sum_{j\neq k}d_jx_T^j)-d_kx_T^k||_F^2\\
=||E_k-d_kx_T^k||_F^2\\
\end{array}

保证剩余误差和已经估计的向量正交

..math::

\begin{array}{l}
E_k^R=E_k\Omega,\\
x_R^k=x_T^k\Omega
\end{array}



算法总结：
========

#.  首先估计稀疏表示，然后估计字典，在字典估计的时候，采用每次只估计一个Dj，其他不变，交替迭代的方法。
#.  和k-means比较近似，首先是不知道任何，随便假设D,估计x，然后由x又开始估计D。

参考：
====

#. 浅谈K-SVD http://www.cnblogs.com/salan668/p/3555871.html

