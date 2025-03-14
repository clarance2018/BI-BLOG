---
title: "如何用DataFocus进行渠道用户质量分析？"
date: "2020-12-08"
categories: 
  - "07"
  - "03"
---

为获得更多有效用户，让产品的收益最大化，我们往往需要根据产品特点来选择重点发行渠道。此时，便需要对各渠道的用户质量进行分析。

今天，我们借助DataFocus来了解一种在游戏产品封测期的、渠道用户质量分析的方法。

> 整体分析

我们先整体了解一下游戏产品在各平台和渠道类型的导入量和收入构成。

> ### 1.1 分析详情

以一款手游为例，产品渠道按平台可分为iOS和Android，按合作方式可分为联运和 CPS。

本文选择了一些常用的渠道，并将其分为四类：iOS、Android（联运，非硬核）、Android官方和Android（联运，硬核）。

> ### 1.2 系统操作

数据导入DataFocus系统后，对数据进行搜索分析，选择图表后设置标签，可直接在图中显示各类渠道名及其占比。

![](images/word-image-16.png)

图表 1各渠道导入量占比

使用公式，对渠道再次分类，以了解iOS和Android两个平台的用户占比情况。

![](images/word-image-17.png)

图表 2 使用公式分类

![](images/word-image-18.png)

图表 3 iOS和Android平台的用户导入量占比

由此，在了解到用户占比以及收入占比后，可以分析出用户的付费能力和用户质量。

> ## 2 渠道排名采用综合评价分析法

接下来，采用“综合评价分析法”，根据指标对各渠道进行排名，从而了解各个渠道的用户质量。

> ### 2.1 分析详情

这里统计了各个渠道的导入量、收入、付费率、 ARPPU、ARPU和第7日加权留存率数据。

为消除这六个变量间的量纲关系，我们先对数据进行标准化处理，再使用客观赋权法的标准差系数权重法，计算各指标的权重，最后对各指标进行排名。

> ### 2.2 系统操作

> #### A、数据标准化处理

因为需要对六个指标进行标准化处理，所以我们先在DataFocus中自定义一个标准化公式，以节省编辑同类型公式的时间。

如下图，此次的标准化处理采用“Z-score标准化”方法，将数据减去平均数后再除以标准差。当标准化后的数值比较接近时，为了便于比较，我们可以调整下数据的范围，如这里统一：“×100+100”

![](images/word-image-19.png)

图表 4 自定义公式“Z-score标准化”

> #### B、确定各指标权重

标准差系数权重法，首先需要计算各指标的离散系数，即用标准差除以平均数。同样，我们创建一个“离散系数”的自定义公式。

![](images/word-image-20.png)

图表 5 自定义公式“ 离散系数”

在搜索模块，使用这两个公式计算各指标离散系数和标准化值。为了方便查看，我们将数据保存为中间表“标准化各渠道数据”。

![](images/word-image-21.png)

图表 6 制作公式列

在搜索模块，选择这张中间表进行分析，对各离散系数求和后，再计算各指标权数，即将各指标的离散系数除以所有指标的离散系数之和。

![](images/word-image-22.png)

图表 7 计算离散系数和

> #### C、计算各指标综合评价值

将各指标的权重乘以标准化后的值，即求得各个渠道的综合评价值。

例如图中，公式“导入量离散系数/离散系数和 ”计算导入量的权重后，乘以标准化的导入值，即获得“导入量”的综合评价值。

![](images/word-image-23.png)

图表 8 计算综合评价值

直接对各指标的综合评价值求和，获得综合评分。

![](images/word-image-24.png)

图表 9 统计综合评分

> #### D、搜索与汇总综合排名

对所需数据进行搜索分析。选择数值表后，分别点击表中对应的列名，即可直接对数据进行降序排序，得到各个渠道各项指标及综合排名。

为使排名更直观，可以给表设置“行索引”或再次进行公式的使用。

![](images/word-image-25.png)

图表 10 查看排名

由此可以了解到各渠道的用户质量。

至此，一种在手游封测期的渠道用户质量分析的方法，就使用DataFocus介绍到这里。其实，同样的分析，系统的操作方式不只一种，大家可以去尝试哦~
