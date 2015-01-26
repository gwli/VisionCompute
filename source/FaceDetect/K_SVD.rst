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

.. math::

   \begin{array}{l}
   ||Y-DX||_F^2=||Y-\sum_{j=1}^Kd_jx_T^j||_F^2\\
   =||(Y-\sum_{j\neq k}d_jx_T^j)-d_kx_T^k||_F^2\\
   =||E_k-d_kx_T^k||_F^2\\
   \end{array}

保证剩余误差和已经估计的向量正交

.. math::

   \begin{array}{l}
   E_k^R=E_k\Omega,\\
   x_R^k=x_T^k\Omega
   \end{array}



算法总结
========

#.  首先估计稀疏表示，然后估计字典，在字典估计的时候，采用每次只估计一个Dj，其他不变，交替迭代的方法。
#.  和k-means比较近似，首先是不知道任何，随便假设D,估计x，然后由x又开始估计D。

参考
====

#. 浅谈K-SVD http://www.cnblogs.com/salan668/p/3555871.html

K-SVD: An Algorithm for Designing Overcomplete Dictionaries for Sparse Representation
=====================================================================================

这种被称为extreme sparse represention，每次只能更新一个原子。

..math:: D^{(n+1)}=D^{(n)}-\eta\sum_{i=1}^N(D^{(n)}x_i-y_i)x_i^T 

.. note::

   这个目前还不太理解，那x是孤立的。

.. code-block:: matlab

    noIt = 200
    [rows,cols]=size(y);
     r=randperm(cols); 
    A=y(:,r(1:codebook_size)); 
    A=A./repmat(sqrt(sum(A.^2,1)),rows,1); 
    D=A;
    X=y;
    K = 50;
    
    for it = 1:noIt
        W=OMP(D,X,4.0/5*rows); 
        R = X - D*W;  %这里包含的应该是误差。  如果是真的，还是应该差不多，如果不是真的，下一次应该包含些。
        for k=1:K
            I = find(W(k,:));
            Ri = R(:,I) + D(:,k)*W(k,I);  % 构成一个虚的向量。
            [U,S,V] = svds(Ri,1,'L');
            % U is normalized
            D(:,k) = U;
            W(k,I) = S*V';
            R(:,I) = Ri - D(:,k)*W(k,I);
        end    
    end

假设他对的，然后更新其中一个。D，W是相互独立的，因此可以估计。

每次只更新一对。这里的约束也可以是D或者W不再变化
