ImageMagick
***********

Introduction
============


imagemagick 是一个超强的库，并且指命令行接口异常的强大，基本上图片处理，画图功能它都已经提供了。可以说是一个cli版的GIMP。 同时它又像其他的linux工具一样，它的功能一种是在编译时通过各种宏来指定。另一种方式那就是采用配置文件。并且采用一定的搜索算法。最先开始在当前文件夹下.magick文件开始。从了一些正常的参数之外，还可以通过+define指定的那些隐性的参数。并且用identify 命令可以读取也可以添加各种的`元数据到图片中 <http://www.exif.org/>`_  `exiv2 <http://exiv2.org/>`_ 同时还能够把这些元数据给strip掉，就像gcc的编译一样。每一个图片本身就是对象，我可以图像的统计信息放在元数据里，放在comments里，并且它支持一些通配符。简单的命令可以用convert,mogrify,display等，脚本可以使用`conjure <http://imagemagick.sourceforge.net/http/www/conjure.html#msl>`_ .%RED%而这个正是想要的一直准备去做的一件事之一。如何实现一个动态搜索接口。win7的文件浏览器功能就不错。自己是不是可以基于开源的文件浏览器改出来一个。%ENDCOLOR%其实imagemagick提供了一整套的命令行，包括管理显示排序方面关于图片的，问题自己如何利用这些。
#. `如何显示那文件属性 <http://www.edbott.com/weblog/2005/06/tip-of-the-day-use-metadata-to-organize-digital-pictures/>`_  可以直接使用identify,convert来查看与编辑图片的属性。
#. `best-free-digital-image-viewer.htm <http://www.techsupportalert.com/best-free-digital-image-viewer.htm>`_ 

计算存储图片两种方式一种是矢量图，它是由一些基本的图元组成，这些图元都是可以有基本数学方程。这样可以数学方程进行放大与缩小这个就是SVG它可以用XML等直接传递，只需要一些特征点。而opengl也采用的这种方式，不同的是采用有限元法来表示各种图形，但是在显示的时候，最终还是还要像素上光栅化的。这就像另一些图，直接就是利用点阵图来表示。opengl可以说这种方式的结合。 并且opengl顶点与最后屏幕点还是不一样的。先连线，然后逐行扫描的。

光栅化的后反矩齿。就是把中界点用半透明化。

color space management
======================


一些美学原理是在以及各种颜色空间都在[[Study.ColorTransform]]。在这里只提到在计算机中，颜色的深度的问题，就是指你用几位来表示一种颜色。同时也还有一个采用量化的过程。其中之一多少个像素点代表真实的一个点。这个是采用率的问题，这个图放大与缩小的时候，会采用到，例如缩放时是直接按点踩，还是说几个点中取中值，还是如何。这个在opengl的光栅化时也同样有这样的问题，在光栅化之本身只有顶点数据的，内部的尺寸大小不同时与纹理的映射关系其实就是采样的过程。你可以指定取最大值，取最小值，或者采用滤波的方式来设置都是可以的。以及颜色本身减少压缩也是这样的。
文件本身存储的字节序的问题在这里都是可以指定所修改的。

并且imagemagick还支持批处理。
通过对imagemagick的学习，对于图像本质有了更深的认识。同时对于各种图片存储方式也有更深的认识。总之一点那就是矩阵式结构不变的。改变的一个像素点有多少个通道。每一个通道需要多少位来表示。所谓压缩不压缩也是指的这些。但是JPEG是如何达到压缩目的呢。是把点给扔了，`把细节的地方点多一些。但是如何来保证像素数，扔掉的像素点是不是要拟合出来，并且还标记出来，哪些点是需要拟合的 <http://www.dgwxx.com/blog/blog_22.html>`_  

在图像与图形的处理过程中两者有时候是不分的，在图像的处理过程中，像素的坐标位置提的不是很多，而在图形的像素点的颜色道是说的少了，更多的是顶点的坐标点。其实每一幅图像都有一个坐标系。要么以顶角为原点要么中心为原点。图像的变换都是这样来的。在建模的时候，就发现各个子系统都会自己的局部坐标系。那个gravity指的就是局部坐标系的原点在哪里。
在图形与图像的处理过程中，并且需要计算整副图像的统计值，然后以这些为初值，进行局部分形处理。一个点的坐标值，颜色值，法向值，切线值，都是很重要的。但是图像与图形的是有区别的，图像的法向以切线是估出来的。而图形则是经过建模精确计算出来的。

对于各种图形都支持一种interlaced 的属性，那就是可以边下载边显示。是文件本身的一种属性，还是某一种图片格式的属性。

图片的显示管理
=====================


 ImageMagick提供import进行截屏操作。montage,display,animate批量化的显示，动画的显示与修改.同时进行格式的转化，动画frame的控制 insert/swap/delete/delay/loop，并且能够直接操作.gif中frame.修改顺序。并且还能折分与提取与合成pdf,还能用来破解pdf.。 做和种可视化对比的利用montage 是非常方便的。根据结果生成各种各样对比图片数据。  并且在XWindows中,display可以指定的显示在哪一个窗口，并且还可以设为哪一个窗口的背景，并且还能实时监控图片的变化，vimdot就是这样实现的。但是如指定缩放呢。还是使用montage的方法。
各种动化教程  http://www.imagemagick.org/Usage/anim_basics/
`我的ImageMagick使用心得 <http://www.charry.org/docs/linux/ImageMagick/ImageMagick.html>`_  使用ImageMagic开发一个照片管理库
   
.. ::
 
   convert *.ppm image%d.jpg
   mogrify -format jpg  *.ppm    see http://www.imagemagick.org/www/mogrify.html
   
   使用convert 可以批量进行种变换与添加边框与签名
   
   ftp://ftp.fu-berlin.de/unix/X11/graphics/ImageMagick/www/sitemap.html
   


图形的变换
===============


compare 比较做的还是比较智能的，直接支持单通道的比较，而不需要先分离然后再比较。并且对于各种特效的变换。例如watermark 添加以及签名以及边框的添加都是高度可定制化与批量化的。另一个那就是图片的隐藏，实现的原理是什么呢，直接进行图片叠加算法，还是只在后面又加了一帧。应该不是又加了不是这种，应该是算法叠加。`Steganography <http://en.wikipedia.org/wiki/Steganography>`_  composite -stegano 直接转化为噪声隐藏位图的低位。然后再恢复按照固定的函数算法再恢复出来。但是这种方法也会受到图片的裁减的破坏。  是不是可以直接把ASCII码当灰度或者unicode码当做灰度值，然后把文字变成图像，同时也研究一个那个小鸭子是如何实现的。

图片的噪声，有各种各样的模型，如何进行添加与去除。这个是图像复原的一个题目。`椒盐噪声与高斯噪声的原理 <http://blog.csdn.net/jia20003/article/details/7181463>`_  对于椒盐噪声，为什么非得是极值。在进行模板设计的时候一般都采用奇数矩阵来代替圆形。

.. csv-table:: 

   `高斯函数 <http://zh.wikipedia.org/wiki/%E9%AB%98%E6%96%AF%E5%87%BD%E6%95%B0>`_  , 高斯函数三个参数，均值，方差，还有一个幅度，均值是由谁得出，而方差为什么是指定的。高斯一般用5x5模板 `图像真实对比，用小图来进行对比，这样的实现会很有意义  <http://vipbase.net/ipbook/chap03.htm>`_  把颜色与看数值直接相结合会更有直接意义，这个方法不错，直接看其灰度值的变化。 , 
   ` hmm-kalman-particle-filtering <http://freemind.pluskid.org/machine-learning/hmm-kalman-particle-filtering/>`_  ,
   -segment ,这个只是从直方图进行分割。,
   -shade的 , 光线效果。对于光线的效果是需要三维的，并且需要法向的，二维图像的法向如何进行计算呢。,
   -Solarize , ` 曝晒算法 <http://courses.washington.edu/hypertxt/cgi-bin/book/pmontage/solarized.html>`_ 模仿最初沥清制图的方法，采用V字型反转就可以了对于曲线或者直方图 , 
   -spread , 算法，在一个有限的范围内随机跳，采取什么样的随机会不同的效果吗，总体看来在水波下情形 ,
   -sharpen , 虽然都是高斯，取高通，还是低通，就看你用哪一部分，你是用3sigma之内就是低通，3sigma之外就是高通了,
   -Swirl , 旋涡效果 ,
   -threshold  -level -modulate, -tint , 这其实也是图像分割的一种 最简单的应用，在过滤的时候会非常的方便 ,threashold用的最大值，level用的最小值，其实就是直方图的输出,-tint 是调整各个分量的多少, -modulate 用的是HSV模型，而前面两个用的是RGB模型,,
   -unsharp , 去除模糊，其实锐化的工具 ,
   -wave , 要么横向，要么纵向，能不能径向 ,
   -virtual pixel , 是不是利用多点来表示一点，具体还不太明白 ,
   roll , 自身左右循环移位与上下循环移位 ,
   -append , 就像字符串拼接一样，把图片接在一起,自动去改文件头,并且能够指定边框，背景 ,
   -average ,-fatten , 把多张图，叠加起，点对点按照不同的规则，就像两张的加减一样 ,
   -affinite , 二维的变换矩阵，但是一个问题，那就是坐标原点在哪里 ,


画图
======


颜色格式可以直接使用名子例如red,black,等也可以使用HTML#XXXXXX格式，也可以使用RGB格式。
画图可以指定大小，xc(xwindow colors),以及背景，方向，以及各种基本的图形，以及填充，边框等，并且能够多次嵌套。

.. csv-table:: 

   -annotate , 添加注注释 ,
   -pointsize , 字体大小 ,
   -stroke , 线条颜色 ,
   -fill , 
   -font , 
   -draw , color 50,50 point/replace/foodfill  ,
   ^ , rectangle ,
   ^ , circle ,
   ^ , text ,
   ^ , Image in/over/out/atop ,
   composite , -compose  合成图片 ,
   -write , 可以保存每一步的中间状态 ,


`display <http://www.imagemagick.org/script/display.php>`_ 命令的用法可以按照slide来播放

`Imagemagick中图片大小转换全攻略 <http://ray.imiddle.net/2008/07/how-to-resize-the-image-in-imagemagick/>`_ 

#. `Table of Contents for Writing With Images <http://courses.washington.edu/hypertxt/cgi-bin/book/tablesall.html>`_ 
