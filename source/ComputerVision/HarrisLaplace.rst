+`Harris-Laplace 原理 <http://en.wikipedia.org/wiki/Harris_affine_region_detector#Harris.E2.80.93Laplace_detector_.28initial_region_points.29>`_ 
===================================================================================================================================================

多尺度Harris角点探测：

%\[{m_l}\left( {\vec p;{\sigma _D},{\sigma _I}} \right) = \det \left( {\Gamma \left( {\vec p;{\sigma _D},{\sigma _I}} \right)} \right) - \kappa t{r^2}\left( {\Gamma \left( {\vec p;{\sigma _D},{\sigma _I}} \right)} \right)\]%

对于特定的尺度
.. math:: \sigma,尺度归一化的Laplacian算子为：

%\[{\Delta_N}L( {\vec p;\sigma}) = \sigma\Delta L({\vec p;\sigma}) = \sigma(L_{xx}( {\vec p;\sigma} ) + L_{yy}({\vec p;\sigma}))\]%


.. math:: L_{xx}$%和 %$L_{yy}是x和y的二阶偏导数。

基于上述知识，Harris-Laplace执行如下两步：
#. 取
.. math:: {m_l}\left( {\vec p;{\sigma _D},{\sigma _I}} \right)的最大值点为感兴趣的点：

%\[\vec p = \mathop {\arg  \max }\limits_{\vec p} {m_l}\left( {\vec p;{\sigma _D},{\sigma _I}} \right),{\sigma _I} = {\gamma ^2}{\sigma _D}\]%

#. 根据
.. math:: {\Delta _N}L\left( {\vec p;\sigma } \right) 的局部极值选择特征尺度：

%\[{\sigma _D} = \mathop {\arg  \min }\limits_{{\sigma _D}} {\Delta _N}L\left( {\vec p;{\sigma _D}} \right)\]%

*这个文章的创新点就在特征尺度选择*。

扩展阅读：`Harris affine region detector <http://en.wikipedia.org/wiki/Harris_affine_region_detector#Harris.E2.80.93Laplace_detector_.28initial_region_points.29>`_ 
