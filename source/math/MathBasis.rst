拓扑学
======

:math:`R^m` 的子集 :math:`X` 的一种性质叫做拓扑性质，如果它等介于一个只利用:math:`X` 的开集的概念与集合论的一些标准既来下定义的性质。

主要研究存在性定理，例如大多数应用的共同特点出现在一个存在定理的证明中，一个存在定理是这样的定理，它断言，某一个大类问题中的每一个，有某种特殊性质的的一个解。 存在定理是拓扑学的基本结构。

主要定理的应用，关于多项式的零点，映射的不动点以及向量场的奇点等的存在定理。也要用于证明紧致性，连通性以及连续性。

拓扑学定义
----------

:math:`R^m` 的子集 :math:`X` 的一种性质叫做拓扑性质，如果它等价于一个只利用 :math:`X` 的开集的概念与集合论的一些标准概念(元素，子集，补集，并集，交集，有限集，无限集等等）来定义的性质，简短的说 :math:`R^m` 的子集X 的拓扑性质就是可以表达X的开集族的性质的那一种性质。


:math:`R^m` 的子集`X`与 :math:`R^n` 的子集 `Y` 叫做拓扑等价（或者同胚），如果存在一个一对一的函数 :math:`f:X->Y` 使得 `f` 连续并且 :math:`f^{-1}:Y-X` 也连续，此外，这函数f叫做拓扑等价(或同胚)

所以是可以利用微分, `连续,有界` 等等来研究拓扑结构。 函数的微分性质。

拓扑学是研究点集与函数的拓扑性质的学科。

连续性就是函数的一个拓扑性质。

紧致性与连通性都是拓扑性质。

别如连通集的补集不连通。

但是牵涉到`X` 或它的子集的诸如大小，形状，角度，长度，面积或者体积等特性，它就不可能是拓扑性质。


不动点理论 :math:`f(x)=x` 就是求不动点的过程。 

线段的每一个自映射至少有一个不动点,那么对于差分方程应该有不少的不动点了。

圆到直线的每一个映射都把某对对径点映成同一个象点。 就一个就是平分问题，

薄煎饼问题
----------

如果 `A` 与 `B` 是同一平面中两个有界区域，那么平面中存在一条直线，它把每个区域分成等面积的两半。 同样如果A是平面中有界区域，那未存在着两条垂直的直线，把A分成面积相等的四份。


一维是区间二维是 `圆片` 平面中一圆C与它的内部并集叫做一个圆片D,圆C叫做D的边界.  

以及绕数，拓扑问题，现在看来都可以通过函数的性质来进行研究。

二维的主要定理
--------------

设 :math:`f:D->P` 是从一圆片到平面的映射，C 是D 的边界圆，并设y 是平面中不在fC上的一点,如果 f|C 在点y处的围线数不为零，则 :math:`y\in{fD}` 也就是存在一点  :math:`\exists x \in D, f(x) =y`

例如树的年轮可以用闭区线同伦。 的函数定义。


`混沌理论 <http://www.mysanco.com/index.php?class=wenku&action=wenku_item&id=109>`_ 
===================================================================================

.. csv-table:: 

   `chaos <ChaosTheory>`_         , `数论 <number theory>`_  , `数学分析  <MathematicalAnalysis>`_  ,
   `张量分析 <TenserAnalysis>`_  ,    ` 复变函数 <ComplexFunction>`_      , `矩阵论 <MatrixTheory>`_  , 
   `近世代数 <ModernAlgebra>`_  ,  , `概率统计与随机过程 <StatisticAndRodom>`_  ,

`盲源分离 <BSS>`_ 

.. csv-table:: 

   `实变函数 <RealVariableFunction>`_   , `集合理论 <SetTheory>`_   ,  `离散数学 <DiscreteMathematics>`_  ,

-- Main.GegeZhang - 08 Feb 2013

.. csv-table:: 

   方均根误差 RMSe=sqrt(sum((Ti-Ai).^2)/n) ,
   方均跟误差函数：std（abs（x1-x0)),x1是求得数据，x0为原始数据 ,

root mean square sqrt（1/N sum（（x1-x0)^2+（y1-y0)^2）） x1 和y1变动起来。
[Direct Position Determination of Multiple Radio Signals]

`随机过程 <StochasticProcesses>`_ 


泛函数分析
==========

主要研究无限维空间（具有各种拓扑）的结构，它间之间的映射以及映射的微积分。

See also
========

#. `mathoverflow <http://mathoverflow.net/>`_  一个不错数学论坛
#. `本科数学专业课程 <http://wenwen.soso.com/z/q132546254.htm>`_  
#. `数学专业的大学课程该怎么学呢？哪些课更重要？ <http://www.guokr.com/question/336540/>`_  
#. `将数系从复平面扩展至三维等高维数空间完全可能 <http://tieba.baidu.com/p/2239450115>`_  在低维复杂的问题，到了高维就变的简单了
#. `超越复数的三元数 ──从复平面到三维数空间 <http://www.pep.com.cn/gzsx/jszx&#95;1/jxyj/gzsxjscg/201012/t20101227&#95;993192.htm>`_  
#. `计算机与数学看看总些一下思路 <http://hi.baidu.com/idardpuajcbiprd/item/c046b072afb061500d0a07f4>`_  
#. `MIT牛人解说数学体系 <http://page.renren.com/698000112/note/761661519>`_  
#. `matth videio web <http://www.uccs.edu/math/student-resources/video-course-archive.html>`_  
#. `国外数学谭程 <http://www.pinterest.com/mathematicsprof/>`_  
#. `Video lectures on Real Analysis? <http://math.stackexchange.com/questions/312492/video-lectures-on-real-analysis>`_  
#. `数学之旅 上海交大 <http://www.icourses.cn.sixxs.org/viewVCourse.action?courseId&#61;62ac994d-13d8-1000-868c-83202360307f#>`_  
#. `图像处理中的数学问题 <http://blog.sciencenet.cn/blog-81613-253111.html>`_  
#. `群论 <http://zh.wikipedia.org/wiki/&#37;E7&#37;BE&#37;A4&#37;E8&#37;AE&#37;BA>`_  
#. `抽象代数 <http://zh.wikipedia.org/wiki/&#37;E6&#37;8A&#37;BD&#37;E8&#37;B1&#37;A1&#37;E4&#37;BB&#37;A3&#37;E6&#37;95&#37;B0>`_  
#. `斯坦福大学公开课 ：机器学习课程 <http://v.163.com/special/opencourse/machinelearning.html>`_  这个和自己下载的应该是配套的
#. `离散优化 <http://c.open.163.com/coursera/courseIntro.htm?cid&#61;174&#38;tabNoJmp&#61;1#/courseIntro>`_  

#. `图像处理的数学方法 <http://blog.csdn.net/tzgj2007/article/details/7461833>`_  
#. `http://www.360doc.com/content/10/1110/22/106832&#95;68338547.shtml <http://www.360doc.com/content/10/1110/22/106832&#95;68338547.shtml>`_  里面的高维图像处理是什么？
#. `天玑学术网 <http://soscholar.com/concept&#95;search/conceptSearchById?concept&#95;id&#61;7f41db47-ae43-5473-7afa-222f5bce2577>`_  看看可以快速找到方向
#. `历年全国优秀博士学位论文评选结果 <http://www.chinadegrees.cn/xwyyjsjyxx/zlpj/yblwpm/>`_  
#. `Petri网 <http://zh.wikipedia.org/wiki/Petri&#37;E7&#37;BD&#37;91>`_ 用于状态分析，工作流设计
#. `科学家怎样做科研 <http://v.163.com/movie/2009/1/V/8/M7SP3BIOT&#95;M7SP3E4V8.html>`_  
#. `运筹学石华 <http://v.163.com/special/cuvocw/yunchouxue.html>`_  
#. `一个数学科普网站 <http://www.mysanco.com/index.php?class&#61;wenku&#38;action&#61;&#38;page&#61;2&#38;k&#61;&#38;menuid&#61;4>`_  
#. `我的学习经验 杨振宁 <http://www.mysanco.com/index.php?class&#61;video&#38;action&#61;videoplay&#38;id&#61;11>`_  
#. `文化科普 <http://songshuhui.net/>`_  
#. `国内建的数学科普网站 <http://mkd.lyge.cn/a160/000.htm>`_  

Thinking
========



数学分析，高等代数，概率论与数理统计，解析几何，常微分方程，实变函数论，复变函数，微分几何，近世代数，数论，我们学校还另外开了数学建模以及经济数学中那个叫啥来着......基本上就这些专业课了，LZ想跨过来的话个人以为数学分析和高等代数要系统的学了，特别是数学分析，没学好这个的话后继课程基本上学了也白搭，加油吧，毅力胜过一切！

-- Main.GangweiLi - 18 Sep 2013


我学的是基础数学，数学分析高等代数解析几何是基础，抽象代数是高代的深入，实变函数又叫实分析是数学分析的深入，加上常微分方程和复变就可以了，拓扑和泛函是研究生的基础，努力学下就可以了~~~我感觉每门都很重要。都是整体，对了，还有微分几何，想学几何的话也是很重要的专业课。

-- Main.GangweiLi - 18 Sep 2013


与其在低维上纠结的事情，放在高维的就变的简单了。最重要的那就是独立思考力。所以能够快速掌握利用计算机来进行推导。可能要真的去看看hackwell语言了。它能更高层面解决你的编程问题。

-- Main.GangweiLi - 19 Sep 2013


梁伟说 图像搜索，视频图像处理现在比较火。

-- Main.GegeZhang - 14 Oct 2013




行列式det的意义是什么？都有哪些用途？

-- Main.GegeZhang - 16 Oct 2013


*建模思路*
`Mathematical_optimization <http://en.wikipedia.org/wiki/Mathematical_optimization>`_ 

#. 建立目标方程
#. 寻找约束条件
#. 利用拉格朗日乘法与KKT来建立解方程式
#. 通过求极值或者解方程来得目标条件
#. 分析目标条件性质，再进一步优化计算，或者寻找简化计算

-- Main.GangweiLi - 24 Feb 2014

