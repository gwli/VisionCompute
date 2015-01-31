-+`希尔伯特转换 <http://zh.wikipedia.org/zh-cn/%E5%B8%8C%E7%88%BE%E4%BC%AF%E7%89%B9%E8%BD%89%E6%8F%9B>`_ 
===============================================================================================================


Hilbert定义如下：

%\[\hat s\left( t \right) = h\left( t \right) \otimes s\left( t \right) = \int\limits_{ - \infty }^\infty  {s\left( \tau  \right)h\left( {t - \tau } \right)d\tau }  = \frac{1}{\pi }\int\limits_{ - \infty }^\infty  {\frac{{{\mathop{\rm s}\nolimits} \left( t \right)}}{{t - \tau }}d\tau } \]%

其中:
%\[h\left( t \right) = \frac{1}{{\pi \tau }}\]%

其频率响应由傅里叶变换给出：

%\[H\left( \omega  \right) = F\left( h \right)\left( \omega  \right) =  - i \cdot {\mathop{\rm sgn}} \left( \omega  \right)\]%

其中F是傅里叶变换，

%\[{\mathop{\rm sgn}} \left( \omega  \right) = \left\{ \begin{array}{l}
1, for \omega  > 0\\
0, for \omega  = 0\\
 - 1, for \omega  < 0
\end{array} \right.\]%

因此Hilbert利用傅里叶变换，使得正频率成分偏移-90度，负频率偏移+90 度。
