色调以及摄影的应用
===========================

眼睛总是被吸引到画面中最明亮的部分（差异最大的那分），例如白底黑主体就相反了。所以亮色调在视觉上优先。要充分利用光线，肤色，以及衣服的颜色的色调来突出主题。

例如深色的衣服有助于使人体与背景浑然一体，这样面部就会成为画面中最最显眼的部分，深色显的苗条，浅色增加分量，一般来说，衣服的颜色应该淡化，因为鲜艳的色彩会影响对面部的注意。
布光
======

布光的原理最终是最终是颜色的设计,人像摄影主要是柔光.
柔光,冷光,䁔光,背景光,轮廓光,发型光,羽化光,光比

窗户光,最好的时候,上午中间,下午的中间时段.
See also
========

#. `LCH，lab <http://wenku.baidu.com/view/e57b9428915f804d2b16c1bf.html>`_  只是不同的颜色模型，并且常见光线与颜色模型值，例如强度与功率等。
#. `Recovering highlights with dcraw using LCH blending <http://people.zoy.org/~cyril/dcraw&#95;lchblend/highlight&#95;recovery&#95;dcraw&#95;lch&#95;patch.html>`_  
#. `摄影用光 色温  <http://wenku.baidu.com/view/e47b1e3343323968011c9295.html>`_  色温中，绿色基本保持不变34％，我们通常指的色温调整主要改变是RB两个的百分比。三者靠近比例接近的时候就是白光也就是日光色温，日光的色温基本是5500k. 黑体色温与CIE的色温定义是有区别的。并且色温也是表征能量，而不是颜色的。不能表达所有颜色。
#. `brucelindbloom <http://www.brucelindbloom.com/>`_  关于颜色各种转换与在线工具
#. `Decoding raw digital photos in Linux <http://www.cybercom.net/~dcoffin/dcraw/>`_  
#. `色彩与色调的调整 <http://wenku.baidu.com/view/33582aaed1f34693daef3ebf.html>`_  要慢慢来看懂这些理论了与实际的用途了
#. `白平衡与直方图均衡化 <http://wenku.baidu.com/view/24632048767f5acfa1c7cd7e.html>`_  这个到底是什么关系呢，是不是对应关系
#. `直方图、对比度调节及白平衡 <http://wenku.baidu.com/view/e3943a36ee06eff9aef80756.html>`_  可以做一下这些实验在，GIMP或者python中
#. `调色教程入门二——色彩基础,想学调色的必看 <http://wenku.baidu.com/view/ab6b8b2ecfc789eb172dc86a.html>`_  要看懂直方图的分布意义了
#. `色温表 <http://blog.sina.com.cn/s/blog&#95;51bce55e0100he89.html>`_  

思考
======



*Hue-Saturation*
   
.. ::
 
   Y = 0.299 * r + 0.587 * g + 0.114 * b;
   U = 0.1687* r - 0.3313* g + 0.5 * b + 128;
   V = 0.5 * r - 0.4187*g - 0.0813*b + 128;
   
   Y=亮度 U=色度 V=饱和度 
   

#. `Y U V introduction <http://www.cnpdb.com/doc/2006-08/1156779961d1630.shtml>`_ 
-- Main.GangweiLi - 12 Aug 2012


*色阶曲线的应用*
现在终于明白曲线坐标的意义了，X轴代表的是原来相素分布，Y代表输出的色采分布。曲线就是一个直接映射关系。 而原始分布是要根据直方图来看，或者直接去图片去测试区域。

-- Main.GangweiLi - 20 Nov 2012



*如何在实践应用*
拿着相机，如何来控制颜色，来达到自己的目的呢。亮度的不同会产生什么，饱和度的会产生什么样的东西，色度的不同会产生什么。

-- Main.GangweiLi - 02 Jan 2013
