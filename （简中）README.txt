# 数据分析项目


## 项目概述

中国和其他国家在联合国气候行动峰会上宣布了碳中和目标，节能是实现这些目标的重要议题之一。而热舒适性分析是优化能源消耗及空调之间平衡的关键因素。

这是以分析及可视化悉尼科技大学 (UTS) 11 号楼的房间02.412（数据竞技场）及 12_431（分析室）的室内环境历史温度和湿度数据集，及运算相应的热舒适指数结果，找出房间使用者的热舒适程度所做的探索性数据分析项目。

项目涵盖的主题：

- 数据收集和操作（NumPy、Pandas DataFrames （数据帧）及（数组）、转换数据类型、数据合并、重新排序列）
- 数据可视化、单变量（分类特征和柱状计数图）及双变量分析（线图、散点图、回归线、jointplot）
- 描述性统计（箱形图、最大值、最小值、平均值、标准差、四分位距（IQR））
- 对外部python工具包的运用
- 用数据叙事


## 数据概述

采用了由2021 年 5 月 1 日至 2021 年 7 月 30 日，由分别位于两个房间内的传感器所收集的温度及湿度的线性数字数据集（请参阅「Images」文件夹）。

「EIF」研究项目的数据传感器接口由Australian Government's Education Investment Fund (EIF) （直译：澳洲政府的教育投资基金）资助，用以监控大厦的可再生能源系统、以及各种外在及内在环境因素。

https://eif-research.feit.uts.edu.au/

https://eif-wiki.feit.uts.edu.au/eif_overview

然而，学院的技术服务经理（Technical Services Manager）告知：由于技术/维护问题（请参阅「Images」文件夹的电子邮件对话），故本项目仅采用温度和相对湿度数据集进行分析。数据集直接从 url 链结复制到 .txt 文件，而非从搜索引擎下载（请参阅「Data」文件夹）。


## 关于热舒适度、预测平均投票数(pmv) 和不满意者的百分比 (ppd)

热舒适度是使用者对环境热量的感觉的满意程度，取决于几个因素，包括但不限于：气温、平均辐射温度、湿度、相对空气速度、新陈代谢率和衣服热阻，本项目将采用由丹麦教授 Povl Ole Fanger 所研发的「pmv/ppd 评价指标」。

简单来说，PMV 是一个用来预测一组使用者的投票平均值的7分制热感觉指数；「PPD」是一个与「PMV」相关的指数，用于预测对热舒适度不满意的使用者百分比。

根据 「ASHRAE 标准 55」，如建筑物内使用者的新陈代谢率在 1.0 met及 1.3 met之间，及衣服提供 0.5 clo 到 1.0 clo 的热阻性的话，「舒适区」代表「预测平均投票数」（pmv）为 - 0.5 到 + 0.5之间 及「不满意者的百分比」（ppd）在10%或以下。

如欲深入了解热舒适理论，请参阅：

https://www.designingbuildings.co.uk/wiki/Predicted_mean_vote

https://www.simscale.com/blog/2019/09/what-is-pmv-ppd/

https://www.designingbuildings.co.uk/wiki/Indoor_air_velocity

https://roastsurvey.com/blog-post/understanding-clo-values/

http://www.sensiblehouse.org/nrg_comfort.htm

https://www.designingbuildings.co.uk/wiki/Operative_temperature


## 假设

须做出以下几个假设以模拟分析项目的背景：

- 空气温度 = 平均辐射温度（成为「运行温度」，假设相对空气速度 = 0.1 m/s，即室内空气和物件表面（例如墙壁、地板、天花板）之间的热传递可忽略不计。）
- 相对空气速度 (vr) = 0.1 m/s（用于简单的热传递计算）
- 衣服热阻（clo）= 1.0 clo（典型的冬季室内服装）
- 新陈代谢率(met) = 1.1 met（打字，两个房间使用者的典型日常工作）


## 方法

首先，对温度及湿度进行操作、分析及可视化，以找出其趋势、它们之间的关系及类别分布。

之后，采用 Python 工具包 – 「pythermalcomfort」、「美国采暖制冷空调工程师协会（ASHRAE）的室内环境热舒适标准」及其理论，运算热舒适指数「pmv & ppd」，并以相似的方式分析和可视化。

https://github.com/CenterForTheBuiltEnvironment/pythermalcomfort

https://pythermalcomfort.readthedocs.io/en/latest/reference/pythermalcomfort.html#predicted-mean-vote-pmv-and-predicted-percentage-of-dissatisfied-ppd

然后，比较「温度和湿度」及「pmv和ppd」指数对使用者的室内热舒适感的代表性。

最后，在一部分给使用者带来「暖/热」时隙时间段内，改变衣服热阻数值，并重新计算「pmv & ppd」指数以查看改善%。


## 目录

1. 提取数据并构建初始数据帧（DataFrame）
2. 对数据进行分类
3. 将所有温度和湿度数据帧合并（merge）为一
4. 数据类别及趋势的可视化
5. 采用「pythermalcomfort」工具包运算 「pmv & ppd」指数及可视化
6. 在房间02-412最初给人「暖/热」感觉的时隙中，采用新的衣服热阻（'clo' ）值
7. 结论


## 关于悉尼科技大学（UTS） 11 号楼

凭借其广泛的「可持续性」特点（能源、用水量等），悉尼科技大学 11 号楼曾经获得澳洲绿色建筑委员会 （GBCA）授予「绿色之星 - 教育设计 v1」的5 星评级。

https://www.uts.edu.au/partners-and-community/initiatives/uts-sustainability/campus-operations/sustainable-buildings

https://www.acts.asn.au/uts-helps-green-sydneys-skyline/

除了可持续性方面，热舒适、空气质量等室内环境因素也对使用者的体验和建筑自身的受欢迎程度起着至关重要的作用。


## 运算热舒适度的便利工具

https://comfort.cbe.berkeley.edu/

如须模拟我的项目中的设置：

- 在图表顶部的选项面板中选择「相对湿度与空气温度」（ 'Relative humidity vs air temperature'）
- 在「Select method」中选择「PMV method」
- 选中「运行温度」（Operative temperature）框
- 尝试不同的「服装水平」（clothing level）和「代谢率」（Metabolic rate）数值，
- 然后输入温度和湿度，例如：

![image](https://user-images.githubusercontent.com/95272183/154760490-073db072-4120-4c13-93d7-682f528180c9.png)
