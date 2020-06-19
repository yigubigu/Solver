# MultiTimeWindowConstraint

## 描述

## 调用JSON格式

```json
{
	"Name": "MultiTimeWindowConstraint",
	"NumberOfNodes": 3,
	"ServiceTimes":{
		"0": 0,
		"1": 10,
		"2": 10
	},
	"TimeWindows":{
		"0": [[50, 70], [100, 120], [150, 180]],
		"1": [[50, 70], [100, 120], [150, 180]],
		"2": [[50, 70], [100, 120], [150, 180]]
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
* ServiceTimes：一维Double数组，节点的服务时长。
* TimeWindows: 一维Double列表数组，节点的服务时间窗。
* PhysicalMap\*：一维Integer数组，将节点映射到物理节点。
* TimeMatrix：二维Double数组，行驶时间矩阵。

注意，每个节点的时间窗序列必须是递增排序。


## 返回JSON格式

```json
{
	"Name": "TimeWindowConstraint",
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
