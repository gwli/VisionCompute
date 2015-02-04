
`机器学习 <machineLearning>`_ 
==================================


对于相机的标定源于 `摄影测量学 <http://jpkt.whu.edu.cn/jpkc2005/syclx/3.class%20online/prscladuc.htm>`_  
`摄相机标定 <http://wenku.baidu.com/view/c0df13d7b9f3f90f76c61be4.html>`_ 

application
===========



.. csv-table:: 

   `ARToolKit <http://www.hitl.washington.edu/artoolkit/>`_  , ARToolKit 它是一个C/C++ 语言编写的库，通过它可以让我们很容易的编写 增强现实 应用程序。增强现实（AR）是将电脑虚拟的图像覆盖到真实世界画面中，这个技术在工业和理论研究方面都存在着极大的潜能。对于开发一个AR程序来说，最困难的部分在于实时的将虚拟图像覆盖到用户视口，并且和真实世界中的对象精确对齐。ARToolKit使用电脑图像技术计算摄像机和标记卡之间的相对位置，从而使程序员能够将他们的虚拟对象覆盖到标记卡上面。ARToolKit 提供的快速和准确的标记跟踪，能够让你快速的开发出许多更新更有趣的AR程序。 ,

在计算机视觉中，一个算法通常需要很多子程序，怎样才能把这些算法综合起来的？还是仿真中只需要一部分？

Introduction
============

#. ` for my computer vision textbook <http://szeliski.org/Book/>`_ 
#. ` washington CS course  <http://www.cs.washington.edu/education/courses/cse576/08sp/>`_ 
#. `加州伯克利大学计算机视觉(Computer Vision) <http://52opencourse.com/97/coursera%E5%85%AC%E5%BC%80%E8%AF%BE%E8%AF%BE%E4%BB%B6-%E5%8A%A0%E5%B7%9E%E4%BC%AF%E5%85%8B%E5%88%A9%E5%A4%A7%E5%AD%A6%E8%AE%A1%E7%AE%97%E6%9C%BA%E8%A7%86%E8%A7%89-computer-vision>`_ 
#. `武大图像处理 <http://video.jingpinke.com/brief?uuid=8a833996-18ac928d-0118-ac929071-03e2>`_ 
#. `Computer Vision Home Page  <http://www.cs.cmu.edu/~cil/vision.html>`_ 
#. `Computer vision <http://szeliski.org/Book/>`_  找到这本书
#. `standford课程 <https://www.coursera.org/course/computervision>`_ 
#. `D.Marr计算视觉理论 <http://baike.baidu.com/view/3328922.htm>`_  
#. ` 圖像及編程常用網址，作為收藏(Very Good) <http://blog.csdn.net/yaoyansi/article/details/5010401>`_ 
#. `视频教程的课件 <http://www.cs.ucf.edu/>`_ 

See also
========

#. `Gabor滤波简介和实现(Matlab，OpenCV)  <http://blog.163.com/huai&#95;jing&#64;126/blog/static/171861983201172091718341/>`_  加窗的傅叶变换
#. `利用并行计算的高效视觉三维场景重建程序：VisualSFM <http://www.bfcat.com/index.php/2013/06/visual-sfm/>`_  
#. `斯坦福大学公开课 ：机器学习课程课件笔记 <http://blog.csdn.net/dcraw/article/details/7712321>`_  
#. `这个网站有很多讲座，可以听一下 新方向 <http://videolectures.net/>`_  
#. `上海机器人展2014 <http://www.ciros.com.cn/#>`_  
#. `机器视觉牛人及其相关领域分类科普 <http://blog.csdn.net/mysteryrat/article/details/9663283>`_  这些怎么用呀

特征匹配
========

ris角点检测->KLTI匹配方法 适合于摄像机运动变化比较小

sift 。当摄像机做大位移和旋转，甚至镜头缩放情况下， 这类方法依然能稳定地抽取和匹配特征点

摄像机自标定
==================

matlab 中的标定问题，我想可以多次迭代，减小误差，但是怎样把这些得到的参数和实际的进行对比，我想这是一个问题，要用opencv进一步的矫正吗？是不是可以设计让机器人躲避障碍物？

自标定 self-calibration
===========================

为了在不估计外参数的情况下，满足一个二次曲线：

.. math:: 
  J=x^TCx=0，

对此x进行求导，得到:

 :math:`l=2Cx`, 则:math:`x=0.5C^{-1}l` ,带入J得到: :math:`l^T\Omega l=0`.

#. `从CVPR2013看计算机视觉研究的三个趋势 <http://www.bfcat.com/index.php/2013/07/compute-visioni-trends/>`_  
#. `计算机视觉（CV）前沿国际国内期刊与会议 <http://blog.sciencenet.cn/blog-337448-411967.html>`_  
#. `斯坦福大学立体视觉 <http://v.163.com/movie/2008/11/7/K/M6TN5NEEU&#95;M6TN75K7K.html>`_  
#. `中科院计算机视觉视频 <http://www.abab123.com/Soft/ShowSoft.asp?SoftID&#61;11659>`_  
#. `视觉增强技术 <http://www.cvchina.info/>`_  

计算机视觉牛人
=====================

#. `Gregory Hager <http://scholar.google.com/citations?view&#95;op&#61;view&#95;citation&#38;hl&#61;en&#38;user&#61;ivApfKcAAAAJ&#38;sortby&#61;pubdate&#38;citation&#95;for&#95;view&#61;ivApfKcAAAAJ:65Yg0jNCQDAC>`_  
#. `David Lowe <http://www.cs.ubc.ca/~lowe/vision.html>`_  
#. `计算机视觉牛人（转载） <http://blog.sciencenet.cn/blog-350420-302989.html>`_  
#. `经典文章计算机视觉 <http://blog.csdn.net/dcraw/article/details/7367990>`_  
#. `机器学习与计算机视觉大牛族谱 <http://blog.csdn.net/shfkuang/article/details/7772935>`_  
#. `CVPR2013感兴趣的文章整理 <http://www.bfcat.com/index.php/2013/03/cvpr2013-papers/>`_  
#. `Coursera公开课课件: 加州伯克利大学计算机视觉(Computer Vision) <http://52opencourse.com/97/coursera&#37;E5&#37;85&#37;AC&#37;E5&#37;BC&#37;80&#37;E8&#37;AF&#37;BE&#37;E8&#37;AF&#37;BE&#37;E4&#37;BB&#37;B6-&#37;E5&#37;8A&#37;A0&#37;E5&#37;B7&#37;9E&#37;E4&#37;BC&#37;AF&#37;E5&#37;85&#37;8B&#37;E5&#37;88&#37;A9&#37;E5&#37;A4&#37;A7&#37;E5&#37;AD&#37;A6&#37;E8&#37;AE&#37;A1&#37;E7&#37;AE&#37;97&#37;E6&#37;9C&#37;BA&#37;E8&#37;A7&#37;86&#37;E8&#37;A7&#37;89-computer-vision>`_  
#. `计算机视觉公开课 <http://coursegraph.com/search&#95;results/computer&#37;20vision>`_  
#. `人工智能MOOC <http://mooc.guokr.com/post/601427/>`_  
#. `Opencv学习网站 有视频 <http://www.opencvchina.com/forum.php?mod&#61;viewthread&#38;tid&#61;1666&#38;extra&#61;page&#37;3D1&#38;page&#61;1&#38;>`_  
#. `OpenCV学习笔记（17）双目测距与三维重建的OpenCV实现问题集锦（二）双目定标与双目校正 <http://blog.csdn.net/chenyusiyuan/article/details/5963256>`_  适用双摄像头在同一平面内
#. `分享一些OpenCV实现立体视觉的经验 <http://blog.csdn.net/u010054675/article/details/9376579>`_  
#. `matlab 标定中的参数 <http://www.vision.caltech.edu/bouguetj/calib&#95;doc/htmls/parameters.html>`_  

#. `SFM bundler <http://www.cs.cornell.edu/~snavely/bundler/>`_  

Thinking
========

*多视角几何学* 例如如何从三视图来恢复出原来图形，那么我就能够多个角度来照片，来恢复三维的图形。首先要知道多个图片中图一点。然后再来恢复。

