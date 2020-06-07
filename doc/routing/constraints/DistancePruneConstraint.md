# DistancePruneConstraint

## 描述

## 调用JSON格式

```json
{
	"Name": "DistancePruneConstraint",
	"NumberOfNodes": 3,
	"RoutePruneThreshold": 1.0,
	"InsertionPruneThreshold": 0.1,
	"ExchangePruneThreshold": 0.1,
	"CrossPruneThreshold": 0.1,
	"ReplacePruneThreshold": 0.1,
	"Latitude":{
		"0": 10.0,
		"1": 10.1,
		"2": 30.0
	},
	"Longitude":{
		"0": 100.0,
		"1": 100.1,
		"2": 200
	}
}
```
* Name: String，名称。
* NumberOfNodes: Integer，节点个数。
* RoutePruneThreshold：Double，两条路径进行邻域搜索的阈值。
* InsertionPruneThreshold：Double，进行插入操作的阈值。
* ExchangePruneThreshold：Double，进行交换操作的阈值。
* CrossPruneThreshold：Double，进行交叉操作的阈值。
* ReplacePruneThreshold：Double，进行替换操作的阈值。
* Latitude：一维Double数组，节点的精度。
* Longitude：一维Double数组，节点的维度。


## 返回JSON格式

无返回

