---
title: lightgbm参数
date: 2017-10-14 13:59:45
tags: [lightgbm,boost,机器学习]
categories: [机器学习]
---

## lightgbm 参数介绍

之前介绍了下xgboost的重要参数。今天把lightgbm的参数整理一下，方便以后查阅。

1. **Core Paramater**
	这是一般会设置的核心参数
	* **objective**: regression, regression_l2(mse), regression_l1(mae), huber, fair, poisson, binary, lambdarank, multiclass
	* **boosting**: gbdt, rf, dart, goss
	* **num_rounds**: boosting的数量
	* **learning_rate**: 学习率
	* **num_leaves**: 单一树中的叶子数
	* **num_threads**: 最好设置为CPU核数

2. **Learning Control Paramater**
	这些是控制学习的一些参数，只选取了个gbdt有关的一些。其他后续补充。
	* **max_depth**
	* **min_data_in_leaf**
	* **min_sum_hessian_in_leaf** : 类似min_data_in_leaf
	* **feature_fraction**：类似xgboost中的colsample_bytree
	* **feature_fraction_seed**
	* **bagging_fraction**：随机选择一部分数据不重新采样
	* **bagging_freq**
	* **bagging_seed**
	* **early_stopping_round**
	* **lambda_l1**
	* **lambda_l2**
	* **min_gain_to_split**：划分节点的最小提升

3. **Metric Parameter**
	* **metric** 评估参数，主要有：l1,l2,l2_root(rmse),huber,fair,poisson,ndcg,map,auc,binary_logloss,binary_error,multi_logloss,multi_error
	* **metric_freq**: 输出频率

还有不少参数暂时没怎么用到，以后再补充。
	
	