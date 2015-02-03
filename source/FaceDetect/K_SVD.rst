K-SVD
*****

这是k-svd，直接使用原图像。

K_SVD算法模型
=============

原始k-SVD模型同时估计稀疏字典和稀疏系数，也就是包含两个未知矩阵：

.. math::

   \min\limits_{D,X}{||Y-DX||_F^2}\;  \;\;subject \;to \forall i, x_i =e_k for some k

其中 :math:`e_k` 是单位阵，这个模型中，每个test图像中向量，只有一个1，其它全为0。但是在实际中，这个约束过分苛刻，为了放松约束，只要求任意图像都可以表示为矩阵D的线性表示，并约束 :math:`x_i` 满足稀疏性，得到：

.. math::

   \min\limits_{D,X}{||Y-DX||_F^2}\;  \;\;subject \;to \forall i, ||x_i||_0\leq T_0

估计X
======
这里因为同时有两个位置矩阵，D 和 X.因此无法得到最优解，这里采用近似追踪方法（approximation pursuit method）。首先假设任意初始矩阵D,估计X. 比如使用OMP算法。

更新dictionary D
=================

因为D是一个矩阵，需要求的元素很多，所以这里采用每次只估计一个 :math:`D_j` 原子，其他 :math:`j\neq k`  不变， 这种被称为extreme sparse represention。用梯度迭代更新的方法表示为：

.. math:: D^{(n+1)}=D^{(n)}-\eta\sum_{i=1}^N(D^{(n)}x_i-y_i)x_i^T 

.. math::

   \begin{array}{l}
   ||Y-DX||_F^2=||Y-\sum_{j=1}^Kd_jx_T^j||_F^2\\
   =||(Y-\sum_{j\neq k}d_jx_T^j)-d_kx_T^k||_F^2\\
   =||E_k-d_kx_T^k||_F^2\\
   \end{array}

抛弃零项，减小SVD估计D和W的计算量，得到：

.. math::

   \begin{array}{l}
   E_k^R=E_k\Omega,\\
   x_R^k=x_T^k\Omega
   \end{array}

核心代码实现：
==============

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
       % As finding the truly optimal X is impossible, we use an approximation pursuit method. 
        R = X - D*W; 
        %这里包含的应该是误差。  如果是真的，还是应该差不多，如果不是真的，下一次应该包含些。
        %%  这里采用分向量估计的方法.
        for k=1:K
            I = find(W(k,:));
            Ri = R(:,I) + D(:,k)*W(k,I);  % 构成一个虚的向量。
            [U,S,V] = svds(Ri,1,'L');
            %重新更新D和W.
            % U is normalized
            D(:,k) = U;
            W(k,I) = S*V';
            R(:,I) = Ri - D(:,k)*W(k,I);
        end    
    end

假设他对的，然后更新每一个原子D。因为D，W是相互依赖的，在后续更新中，要同时更新。


算法总结:
==========

#.  首先估计稀疏表示，然后估计字典，在字典估计的时候，采用每次只估计一个Dj，其他不变，交替迭代的方法。
#.  和k-means比较近似，首先假设随机矩阵D,估计x，然后由x又开始估计D。


算法缺点：
=========

#. 这个算法无法得到全局最优点，只能得到局部最优点。但是实际操作中，这个效果还不错。

#. 这个KSVD用在哪那？我想可以用在识别上。把所有每一副图像都拉成向量，但是这里是基于图像任意排列的情况，只是一些抽象的结果，没有实质性意义，比如无法得到人脑识别到的轮廓信息。

参考：
======
#. http://en.wikipedia.org/wiki/K-SVD

#. 浅谈K-SVD http://www.cnblogs.com/salan668/p/3555871.html

#. K-SVD: An Algorithm for Designing Overcomplete Dictionaries for Sparse Representation


