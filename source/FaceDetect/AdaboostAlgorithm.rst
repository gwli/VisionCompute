+`Adaboost 算法 <http://blog.csdn.net/haidao2009/article/details/7514787>`_ 
==============================================================================


这个算法思想就是每一次分类都是弱分类器，然后通过多次分类，最终形成一个强分类器。

算法具体步骤是：

#. 给定一定的训练集合，
.. math:: (x_1,y_1),...,(x_m,y_m)$%,其中 %$x_i \in X, y_i\in Y=\{-1,1\}

#. 首先初始化分类器：
.. math:: D_1(i)=1/m
#. 训练弱分类器使用D_t分布。
#. 得到弱分布假设
.. math:: h_t:X\rightarrow \{-1,1\},得到误差：

    %\[\varepsilon=Pr_{i\sim D_t}[h_t(x_i)\neq y_i]\]%

#. 选择:%\[\;{\alpha _t}{\rm{ = }}\frac{1}{2}ln(\frac{{1 - {\varepsilon _t}}}{{{\varepsilon _t}}})\]%

#. 更新：

%\[\begin{array}{c}
{D_{t + 1}}\left( i \right) = \frac{{{D_t}\left( i \right)}}{{{Z_t}}} \times \left\{ \begin{array}{l}
{e^{ - {a_t}}}  {\rm{if}} {{\rm{h}}_t}\left( {{x_i}} \right){\rm{ = }}{y_i}\\
{e^{{a_t}}}    {\rm{if}} {{\rm{h}}_t}\left( {{x_i}} \right) \ne {y_i}
\end{array} \right.\\
 = \frac{{{D_t}\left( i \right)\exp \left( { - \;{\alpha _t}{y_i}{h_t}\left( {{x_i}} \right)} \right)}}{{{Z_t}}}
\end{array}\]%

#. 输出最后的假设：
%\[H\left( x \right) = sign\left( {\sum\limits_{t = 1}^T {{\alpha _t}{h_t}\left( x \right)} } \right)\]%

进一步的在人脸中的应用参考`Adaboost原理、算法以及应用 <http://www.zhizhihu.com/html/y2009/565.html>`_ 
