直方图：
********

introduction
============

直方图特点：计算量比较小，直方图反映的是图像像素灰度值的概率分布，

原理：为了改善图像过亮或者过暗，得到图像的理想整体对比度（1/n），通过符合求导的逆推，得到要用积分图像。

优点：适用于图像过亮或者过暗，尤其对于X光图像中更好的骨骼结构

缺点：对处理的数据不加选择，它可能会增加背景杂讯的对比度并且降低有用信号的对比度。

matlab实现：histeq函数。

#. `RGB转灰度图的几种算法 <http://bbs.ednchina.com/BLOG&#95;ARTICLE&#95;1999487.HTM>`_  RGB转换为灰度图完全是我们心理的作用.

#. `50 RGB向灰度转换的原理 <http://hi.baidu.com/mkprlwjxsqbaciq/item/1fcac0858be9b6c29b255f96>`_  可以看一下

直方图本身反映了，各个灰阶的像素的数量，把一幅图像像素看成是一个小球，而像素的灰度看成小球的大小。而灰级就是256个大小从小到大排列的篮子。然后按照顺序把每一个像数按照大小放入合适的篮子里。每个篮子里小球的个数，再除以总数，这样就形成直方图。但是通过直方图发现，小图分布的不均匀。
那么如何算是均匀呢，当然是根据能力与出身了。例如篮子大小当做出身。也就是从小到大的顺序不能变，不管我有多少小球。但是我的灰度又要能体现数量的多少。数量越多，灰度级越大。能同时满足这两个要求。就是要利用概率密度了。这样的结果是首尾的值是不会变的。最小值还是最小值。最大值还是最大值。最小值再加上最小值与当值之间密度差值。

`直方图拉伸和均衡 <http://www.google.com.hk/url?sa=t&rct=j&q=%E7%A9%BA%E9%97%B4%E6%BB%A4%E6%B3%A2%E5%99%A8%2Bmatlab%2B%E5%87%BD%E6%95%B0&source=web&cd=10&ved=0CGEQFjAJ&url=http%3a%2f%2flms%2ectl%2ecyut%2eedu%2etw%2fblog%2flib%2fread_attach%2ephp%3fid%3d46960&ei=txXIUZ2rH4fIlQXrloDwCw&usg=AFQjCNFBNmscYk88KkQC36pbWCKok0-tfA&bvm=bv.48293060,d.dGI&cad=rjt>`_  这里有一个直方图拉伸和均衡的关系，可以看到均衡是拉伸方法的特殊情况，另外可以看到因为增加了对比度，所以都会出现对比度增加的好处，但是这样的话，同时也可能把北京增加了，通过`图像增强1：对比度增强与直方图变换   <http://lijiwei19850620.blog.163.com/blog/static/97841538201210239635623/>`_ 看到，理想的曝光是一个中间高，两边低的灰度情况（这个是为什么还不清楚），大致和直方图均衡的图比较吻合了。


.. graphviz::

   digraph{
   rankdir=LR
   node [shape=box];
   From_picture_histogram->too_Dark->Right_stretching
   From_picture_histogram->bright->Left_stretching
   From_picture_histogram->"Low-contrast_mid-gray-level"->Left_right_stretching
   }
   

` OPenCV直方图均衡化 <http://blog.csdn.net/luomaojiang/article/details/8601321>`_ 这里两个图看很形象直观。但是观点是做的，那就是均衡化不会每个灰度级上都具有相同的象素点数过程。原来每一个篮子的小球的数量是不会改变的，会改变的，只是让原来篮子的大小，随着之进行改变。
`直方图维基定义 <http://zh.wikipedia.org/wiki/%E7%9B%B4%E6%96%B9%E5%9B%BE%E5%9D%87%E8%A1%A1%E5%8C%96>`_ 这里给出的定义，扩展常用的亮度。也就是概率最大的亮度之间的差值。

所以直方图均衡化只改变宽度，不改变形状。同时我们也指定均衡化的宽度。
