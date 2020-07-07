# Algorithm

## 描述

目前求解器内置了三个算法：
* 禁忌搜索（TabuSearch）。调用名称为"TabuSearch"。
* 自适应大规模邻域搜索（Adaptive Large Neigborhood Search， ALNS）。调用名称为"ALNS"。
* 连续逼近算法（Successive Approximation Algorithm）。调用名称为"SuccessiveApproximation"。该算法适用于车型选择比较复杂的情况，不适用于单车型的算例。调用该算法需要同时指定[Greedy](Greedy.md)项目和[LocalSearchOperator](../operators/LocalSearchOperator.md)项目。同时，该算法不支持约束[TimeWindowQueueConstraint](../constraints/TimeWindowQueueConstraint.md)和[TimeWindowQueueReleaseConstraint](../constraints/TimeWindowQueueReleaseConstraint.md)。因为该算法需要多次调用禁忌搜索算法，所以该算法运行时间较长，建议缩短每一次禁忌搜索运行时间。

可以在调用的json对象里指定多个算法的名称，求解器将依次运行指定的算法，上一个算法优化得到的解是下一个算法的初始解，最终返回以此优化后得到的最好的解。

## 调用JSON格式

```json
["ALNS", "TabuSearch"]
```
* ：String列表，调用算法的名称。
