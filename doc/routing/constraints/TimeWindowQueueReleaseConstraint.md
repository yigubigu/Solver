
# TimeWindowQueueReleaseConstraint

## 描述


该约束目前支持的算子仅包括：
* [RelocateBase](../operators/RelocateBase.md)；
* [ExchangeBase](../operators/ExchangeBase.md)；
* [RelocateCluster](../operators/RelocateCluster.md)；
* [ExchangeCluster](../operators/ExchangeCluster.md)；

构造[Nodes](../common/Nodes.md)对象时，最好指定节点的优先级。例如，可以根据节点的最晚服务时间的先后指定节点的优先级。

## 调用JSON格式

```json
{
	"Name": "TimeWindowQueueReleaseConstraint",
	"NumberOfNodes": 3,
	"LatestStartTimes":{
		"0": 1000,
		"1": 100,
		"2": 300
	},
	"EarlistStartTimes":{
		"0": 0,
		"1": 10,
		"2": 20
	},
	"ServiceTimes":{
		"0": 0,
		"1": 10,
		"2": 10
	},
	"LoadingTimes":{
		"0": 0,
		"1": 20,
		"2": 20
	},
	"ReleaseTimes":{
		"0": 0,
		"1": 5,
		"2": 10
	},
	"PhysicalMap":{
		"0": 0,
		"1": 1,
		"2": 2
	},
	"TimeMatrix":{ 
		"0":{
			"0": 0.0,
			"1": 1.0,
			"2": 2.0
		},
		"1":{
			"0": 1.0,
			"1": 0.0,
			"2": 1.0
		},
		"2":{
			"0": 2.0,
			"1": 1.0,
			"2": 0.0
		}
	}
}
```
* Name: String，名称。
* NumberOfNodes: Integer，节点个数。
* LatestStartTimes：一维Double数组，节点的最晚服务开始时间。
* EarlistStartTimes：一维Double数组，节点的最早服务开始时间。
* ServiceTimes：一维Double数组，节点的服务时长。
* LoadingTimes：一维Double数组，节点的货物在仓库的装货时长。
* PhysicalMap\*：一维Integer数组，将节点映射到物理节点。
* TimeMatrix：二维Double数组，行驶时间矩阵。


## 返回JSON格式

```json
{
	"Name": "TimeWindowQueueReleaseConstraint",
	"Coefficient": 0,
	"Feasibility": true,
	"Cost": 0,
	"Sequence":[
		{
			"ID": 0,
			"Arrive": 0,
			"Leave": 0,
			"ServiceTime": 0,
			"EarliestServiceTime": 0,
			"LatestServiceTime": 1000
		},
		{
			"ID": 1,
			"Arrive": 10,
			"Leave": 20,
			"ServiceTime": 10,
			"EarliestServiceTime": 0,
			"LatestServiceTime": 1000
		}
	]
}
```

* Name: String，名称。
* Coefficient：Double，约束的系数。
* Feasibility：Boolean，路径是否满足约束。
* Cost：Double，违反的惩罚成本。
* Sequence：每个节点关于这个约束的属性。
	+ ID：Integer，节点的编号。
	+ Arrive：Double，到达时间。
	+ Leave：Double，离开时间。
	+  ServiceTime：Double，服务时长。
	+ EarliestServiceTime：Double，最早服务开始时间。
	+ LatestServiceTime：Double，最晚服务开始时间。

