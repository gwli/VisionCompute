
退火算法设计的本初：改进非凸问题中`爬山算法 <http://www.cnblogs.com/heaad/archive/2010/12/20/1911614.html>`_ 中的局部最小点。


方法：模拟自然中退火的方法，通过随机交换，求出任意两个点之间的传输距离。我想和便利算法有什么区别？ 还有什么缺点？并用`内循环终止准则，或称Metropolis抽样稳定准则（Metropolis 抽 样准则） <http://www.google.com.hk/url?sa=t&rct=j&q=+Metropolis+%E6%8A%BD+%E6%A0%B7%E5%87%86%E5%88%99&source=web&cd=4&ved=0CD8QFjAD&url=http%3a%2f%2fjingpin%2eszu%2eedu%2ecn%2fyunchouxue%2fziliao%2fkejian%2f%25E7%25AC%25AC10%25E7%25AB%25A0-%25E6%2599%25BA%25E8%2583%25BD%25E4%25BC%2598%25E5%258C%2596%2eppt&ei=JyHEUYOcMY_ZkgWPq4GYAw&usg=AFQjCNG1kEOdSgfjKesiOxiDiT8E4u4ZBQ>`_ 蒙特卡洛实验来是系统达到平稳。

解决问题： `货郎担问题 <http://www.vckbase.com/index.php/wv/1196>`_ ，每次只能选择一个地方，也就是交换一个地方。遍历算法在这个问题中式难以解决的。
`matlab 代码 <http://wenku.it168.com/d_000326627.shtml>`_ 。


优缺点：

#. 优点：计算过程简单，通用，鲁棒性强，适用于并行处理，可用于求解复杂的非线性优化问题。
#. 缺点：运算量较大，下降速度和收敛稳定性的矛盾，下降速度过大，可能出现震荡。下降速度过慢，运算量大。

`退火算法的改进 <http://baike.baidu.com.cn/view/335371.htm>`_  比如采用变化的熟练速度和刚开始收敛速度比较快，基本稳定后采用小收敛速度。

* 思考：和图论中 *最短路径算法*, *剪枝算法* , *最小逆序数*


K-means 算法=expection maximum （EM）期望最大
=====================================================

就是一个分类器的设计
#. `深入浅出K-Means算法  <http://www.csdn.net/article/2012-07-03/2807073-k-means>`_  K means 中K的选择，初始值的选择，里面都有。

See also
========


#. `基于生物进化的遗传算法概述 <http://www.zjubiolab.zju.edu.cn/lesson/userfiles/file/&#37;E4&#37;BA&#37;A4&#37;E5&#37;8F&#37;89&#37;E5&#37;AD&#37;A6&#37;E4&#37;B9&#37;A0&#95;&#37;E7&#37;94&#37;B5&#37;E6&#37;B0&#37;94&#37;E5&#37;AD&#37;A6&#37;E9&#37;99&#37;A2&#37;E6&#37;9E&#37;97&#37;E5&#37;B3&#37;B0.pdf>`_  这里面有遗传算法在各领域的应用
#. ` De Jong&#39;s function 1 <http://www.geatbx.com/docu/fcnindex-01.html>`_  这个函数有多个局部最优点，一般用来作为算法局部最小点的例子
#. `退火算法 <http://baike.baidu.com.cn/view/335371.htm>`_  
#. ` <http://blog.sciencenet.cn/blog-1225851-761882.html>`_  
#. `大数据时代的机器学习热点——国际机器学习大会ICML2013参会感想 <http://blog.sciencenet.cn/blog-1225851-761882.html>`_  看不太懂，有空看看
#. `最大似然参数估计 <http://nbviewer.ipython.org/github/unpingco/Python-for-Signal-Processing/blob/master/Maximum&#95;likelihood.ipynb>`_  

Thinking
========

*模式* 描绘子的组合。


基于决策理论，基于神经网络，基于机器学习。


`西安电子科技大学陈渤 <http://web.xidian.edu.cn/bchen/index.html>`_  我电子所的，主要做大数据分析和机器学习 和图像识别。

`高新波 <http://web.xidian.edu.cn/xbgao/>`_  他做的方向比较新，可以看一下。

