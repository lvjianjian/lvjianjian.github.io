---
title: xgboost参数
date: 2017-10-13 20:46:10
tags: [xgboost,boost,机器学习]
categories: [机器学习]
---
## xgboost 参数介绍
这里记录下xgboost的一些重要参数，方便以后查阅。

#### Task 参数
1. **objective**
	定义学习目标, 默认值为 reg:linear
	* reg:linear  —— 线性回归
	* reg:logistic —— 逻辑回归
	* binary:logistic —— 二分类逻辑回归，输出概率
	* binary:logitraw —— 二分类逻辑回归，输出w<sup>T</sup>x（logistic转换前的得分）
	* count:poisson —— 计数数据的泊松回归，输出泊松分布的均值（max_delta_step默认设置为0.7）
	* multi:softmax —— 多分类，需要设置num_class
	* multi:softprob —— 多分类，输出在各个类别下的概率
	* rank:pairwise —— 任务排序，通过最小化pairwise loss求解
2. **base_score**
	所有实例、global bias的最初预测得分，默认0.5
3. **eval_metric**
	评估指标，不用objective有不同的默认值
	* rmse
	* logloss
	* error 错误率
	* merror 多分类错误率
	* mlogloss
	* auc
	* ndcg  (normalized discounted cumulative gain)
	* map 平均准确率
	* ndcg@n；map@n；ndcg-；map-；ndcg@n-；map@n-

#### booster 参数
1.  **eta**：为了防止过拟合，更新过程中用到的收缩步长。在每次提升计算之后，算法会直接获得新特征的权重。 eta通过缩减特征的权重使提升计算过程更加保守。缺省值为0.3。 类似学习率
2.  **gamma** : 默认值为0，为了对树的叶子节点做进一步的分割而必须设置的损失减少的最小值。该值越大，算法越保守
3. **max_depth**: 树的最大深度
4. **min_child_weight**：树的叶子节点最小权重
5. **max_delta_step**：如果该值为0，就是没有限制；如果设为一个正数，可以使每一步更新更加保守通常情况下这一参数是不需要设置的
6. **subsample**：选取子样本的比率
7. **colsample_bytree**： 选取的特征的比率
8. **lambda**：l2正则
9. **alpha**：l1正则

#### 一般参数
1. **booster**: gbtree和gblinear。gbtree使用基于树的模型进行提升计算，gblinear使用线性模型进行提升计算。缺省值为gbtree。还有一个dart。
2. **silent**: 取0时表示打印出运行时信息，取1时表示以缄默方式运行，不打印运行时信息。缺省值为0。
3. **nthread**: 运行时的线程数。缺省值是当前系统可以获得的最大线程数。

一般会设置 objective,eval_metric,eta,max_depth,subsample,colsample_bytree
防止过拟合还会设置 gamma,min_child_weight,lambda,alpha
silent一般设置为1







