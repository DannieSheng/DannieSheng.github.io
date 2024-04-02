---
title: 'Financial Credit Risk Management'
date: 2024-04-02
permalink: /posts/2024/04/risk-management
tags:
  - Financial
  - Risk Management
---

信贷业务模型维度
======

1. 贷前模型
------
A卡 (Application scorecard) 申请评分卡

2. 贷中模型
------
B卡 (Behavior scorecard) 行为评分卡

3. 贷后模型
------
C卡 (Collection scorecard) 催收评分卡

4. 反欺诈模型
------

5. 画像模型
------


变量筛选的技术指标
======

基于缺失率 (Missing Rate)

基于变异系数 (Coefficient of Variation，CV)

基于稳定性 (Population Stability Index，PSI)

基于信息量 (Information Value，IV)

基于RF/XGBoost特征重要性 (Feature Importance)

基于线性相关性 (Linear Correlation)

基于多重共线性 (Multicollinearity)

基于逐步回归 (stepwise)

基于P-Vaule显著性检验

评分卡评估
======

区分度
------
Gini  
AUC  
KS  

稳定性
------
PSI (群体稳定性指标)

排序性 (Ranking)
------
统计bad_rate、lift、Odds等指标，按照评分分数进行分箱。

拟合度 (Goodness of Fit)
------


其他
======

卡方分箱 (有监督分箱)
------
卡方检验就是对分类数据的频数进行分析的一种方法，它的应用主要表现在两个方面：**拟合优度检验**和**独立性检验（列联分析）**。
### 拟合优度

拟合优度是对一个分类变量的检验，即根据总体分布状况，计算出分类变量中各类别的期望频数，与分布的观察频数进行对比，判断期望频数与观察频数是否有显著差异，从而达到对分类变量进行分析的目的。比如，泰坦尼克号中我们观察幸存者是否与性别有关，可以理解为一个X是否与Y有必然联系。

### 独立性检验

独立性检验是两个特征变量之间的计算，它可以用来分析两个分类变量是否独立，或者是否有关联。比如某原料质量和产地是否依赖关系，可以理解为一个X与另一个X是否独立。

### 卡方检验步骤

(卡方检验的步骤其实就是一般假设检验的过程)

1. 提出假设，比如假设两个变量之间独立
2. 根据分类的观察频数计算期望频数
3. 根据卡方公式，计算实际频数与期望频数的卡方值
4. 根据自由度和事先确定的显著性水平，查找卡方分布表计算卡法值，并与上一步卡方值比较
5. 得出结果判断是否拒绝原假设

卡方分箱是基于**独立性检验**的应用。

### 卡方分箱步骤
- 初始化

根据连续变量值大小进行排序
构建最初的离散化，即把每一个单独的值视为一个箱体。这样做的目的就是想从每个单独的个体开始逐渐合并。
- 合并
  - 计算所有相邻分箱的卡方值：也就是说如果有1,2,3,4个分箱，那么就需要绑定相邻的两个分箱，共三组：12,23,34。然后分别计算三个绑定组的卡方值。
  - 从计算的卡方值中找出最小的一个，并把这两个分箱合并：比如，23是卡方值最小的一个，那么就将2和3合并，本轮计算中分箱就变为了1,23,4。

  **基本思想**：如果两个相邻的区间具有非常类似的类分布，那么这两个区间可以合并。否则，它们应该分开。低卡方值表明它们具有相似的类分布。

- 停止条件

  - 卡方停止的阈值
  - 分箱数目的限制
  
Reference
------

[漫谈信贷业务模型体系建设](https://zhuanlan.zhihu.com/p/370534836)   
[一文看懂风控模型的所有（应该）](https://falbang.com/?p=350)  
[一文带你了解风控评分卡模型](https://developer.kingdee.com/article/289708643615246080?productLineId=29&isKnowledge=2&lang=zh-CN&islogin=true,true&global=1) (各种指标名称)  
[特征稳定性指标PSI的原理与代码分享](https://cloud.tencent.com/developer/article/1947627?areaId=106001)  
[一文介绍特征工程里的卡方分箱，附代码实现](https://cloud.tencent.com/developer/article/1530232)  
[特征工程 | 信息价值IV与群体稳定性PSI](https://blog.csdn.net/richardsz_/article/details/123777141)
[风控模型—WOE与IV指标的深入理解应用](https://zhuanlan.zhihu.com/p/80134853) (贝叶斯角度)
[2.2万字，一文看懂风控模型所有](https://www.zhihu.com/tardis/zm/art/143472559?source_id=1005)