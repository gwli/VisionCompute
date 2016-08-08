流程与发展思路
==============

------
阶段 一 三维点的重构      
------
这个是基础，相标的标定，内外参数问题，以及多视图中同一点判断以及特征点提取都是为解决这个问题。

------
阶段 二  聚类 /建模
------
对于简单的模型就可以这些点进行建模了，计算几何，三角化等等方法点线面建模了。
对于大的复杂的物体来说，那先分块了，也就是聚类问题，对于二维的图像就是图像分割，而于三维点以及更加通用就是聚类算法。


------
-阶段 三  判别器
------
对于分好块的空间类来进行判别是属于物体，简单几何判断解决了这些问题，例如判别这块的特征点是头部信息呢。而不是脚呢。
这个需要运用深度学习的神经网络来进行模糊判断了。
等判别好之后，再根据子块进一步的进行细化。

当然阶段 二与三不断的进行反复迭代分形一样，例如先认出来头，然后再认出五官。


------
阶段 四  动作捕捉
------
走到这一段，就可以做动作的捕捉与分析了。

------

行为分析 
------

能够实现动作捕捉，再进一步进行为的分析，例如利用人的走路习惯来判断一个人的行为。
[[摄像机模型]]
===================


[[基础矩阵]]
================


`重复性准则 <repeatilityRate>`_ 
=================================


`三视图几何 <threeViewGeometry>`_ 
==================================

[[RANSAC]]
==========

`脸部识别 <FaceIdentification>`_ 
=================================

刚体变换和仿射变换：
====================


刚体变换是放射变换的一种特殊情况。刚体变换就是保证长度和角度正交。比如在黄丽芬的变换中，就是一个刚体，如果旋转矩阵被一个任意奇异矩阵替换，就变成了仿射变换。因此刚体变换就是放射变换的一种特殊情况。其实放射变换也是一种线性变换，目的就是保持源图像中的直线和圆保持不变，是一个旋转，收缩加平移的过程。在Opencv中有关于affine transform 的一些code。

齐次坐标主要是为了区分点和向量而设置的，并且方便进行反射变换。

投影变换，我觉得就是图像在现实的图像和实际的成像出来的比例吧。

理想的透视模型满足针孔摄像机模型。对三维空间的一个点（X,Y,Z）,投影到二维投影平面的坐标为（x,y）,上述投影过程可以表示为：
#. `用单张2D图像重构3D场景 <http://blog.csdn.net/zouxy09/article/details/8083553>`_  我想未来的趋势结合红外和光学信息，光学镜头用来获取感光信息，雷达用来获得距离信息
#. `3D重构总资讯 <http://www.cvchina.info/tag/3d-reconstruction/>`_  有空看下别人做的吧
#. `仿射变换(Affine Transformation) <http://blog.sciencenet.cn/blog-605185-672291.html>`_  
#. `深入探索透视投影变换(转) <http://blog.csdn.net/hoyi&#95;liu/article/details/4288443>`_  这个对于齐次变换和投影变换讲的比较清楚，看一下
#. `如何根据相机的参数知道摄像机的内参数矩阵 <http://blog.csdn.net/hjchjc520/article/details/4133515>`_  
#. `立体视觉基础 <http://www.neuroforge.co.uk/index.php/77-tutorials/79-stereo-vision-tutorial>`_  
#. `Computing a disparity map in OpenCV <http://css.dzone.com/articles/computing-disparity-map-opencv>`_  opencv计算视差
#. `how to find disparity of two stereo images in degree <http://stackoverflow.com/questions/14705420/how-to-find-disparity-of-two-stereo-images-in-degree>`_  两幅图像中找到视差
#. `视差估计方法综述 <http://qizengyi.blog.hexun.com/15033468&#95;d.html>`_  
#. `stereo网站 <http://vision.middlebury.edu/stereo/>`_  
#. `在OpenCV中用cvCalibrateCamera2进行相机标定(附程序) <http://www.opencv.org.cn/forum.php?mod&#61;viewthread&#38;tid&#61;4603&#38;highlight&#61;&#37;E6&#37;A0&#37;87&#37;E5&#37;AE&#37;9A>`_  
#. `calibrate.py&#64;5549 <https://code.ros.org/trac/opencv/browser/trunk/opencv/samples/python2/calibrate.py?rev&#61;5549#L51>`_  标定opencv
#. `深圳先进技术研究院 <http://www.siat.cas.cn/jgsz/kyxt/jcs/yjdy/znfs&#95;50599/xwdt/>`_  
#. ` 使用OpenGL对单幅照片进行三维重建 <http://blog.csdn.net/xeric&#95;w/article/details/5867254>`_  
#. `Interactive 3D Graphics <https://www.udacity.com/wiki/cs291/downloads#cs291-video-downloads>`_  交互三维图形 video
#. `3D角色动画 <http://184.82.230.86:5765/foswiki/Study/LeapMotion>`_  
#. `Alexei (Alyosha) Efros <http://www.eecs.berkeley.edu/~efros/>`_  My research is in the area of computer vision and computer graphics, especially at the intersection of the two
#. `计算机视觉、机器学习相关领域论文和源代码大集合--持续更新 <http://blog.csdn.net/zouxy09/article/details/8550952>`_  
#. `CV牛人 <http://www.sigvc.org/bbs/thread-548-1-1.html>`_  
#. `Multi-View Stereo for Community Photo Collections <http://grail.cs.washington.edu/projects/mvscpc/>`_  华盛顿大学三维重构
#. `Robot data set Data for development of accurate computer vision methods <http://roboimagedata.imm.dtu.dk/>`_   计算机视觉数据集
#. `脸部识别数据集 <http://www.face-rec.org/>`_  
#. `图像数据集 <ISL. 2009. Image Databases.>`_  现在还没有仔细看
#. `立体匹配算法介绍 <http://cvchina.net/post/7.html>`_  

图像处理领域如果能够和3D打印结合起来，我想会有很大作用的

-- Main.GegeZhang - 02 Aug 2013


这个里面用了运动模型，但是我真的 不知道什么是3D重构？

-- Main.GegeZhang - 21 Aug 2013


为什么有的图片无法打开。 

-- Main.GegeZhang - 02 Sep 2013


什么是图像下采样 downsamples ？ 目前来看，下采样就是数据大小变小了

-- Main.GegeZhang - 04 Sep 2013


标定就是了解摄像机参数，实现对未来图像预测

-- Main.GegeZhang - 02 Dec 2013




*直接全用2D照片来恢复3D物体*  其中之一那就是image based modeling. C:\快盘\gameEngine\modeling\paper  现在已经很火了。看来现在要抓紧时间把计算机视觉给整理出来。



-- Main.GegeZhang - 21 Apr 2014

SFM
====

从一堆照片中重建三维信息，把二维变成三维。当然用来重建地图也不是错的。


 `Structure from Motion and 3D reconstruction on the easy in OpenCV 2.3+ &#91;w/ code <http://www.morethantechnical.com/2012/02/07/structure-from-motion-and-3d-reconstruction-on-the-easy-in-opencv-2-3-w-code/>`_ ] 实现3D重构opencv
