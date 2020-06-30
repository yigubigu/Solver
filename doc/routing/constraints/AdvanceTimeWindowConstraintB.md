# AdvanceTimeWindowConstraintB

## 描述

## 调用JSON格式

```json
{
	"Name": "AdvanceTimeWindowConstraintB",
	"NumberOfNodes": 3,
	"NumberOfVehicles": 2,
	"Speed": {
		"0": 1.5,
		"1": 1
	},
	"ServiceTimes":{
		"0": 0,
		"1": 10,
		"2": 10
	},
	"NodeTimeWindows":{
		"0": [[50, 70], [100, 120], [150, 180]],
		"1": [[50, 70], [100, 120], [150, 180]],
		"2": [[50, 70], [100, 120], [150, 180]]
	},
	"DeliveryTimeWindows":{
		"0": [500, 1000],
		"1": [1000, 1300],
		"2": [1200, 1440]
	},
	"VehicleTimeWindows":{
		"0": [0, 1000],
		"1": [100, 2000]
	},
	"GroupServiceTimes":{
		"0": 0,
		"1": 10,
		"2": 10
	},
	"GroupMap":{
		"0": 0,
		"1": 1,
		"2": 1
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
* NumberOfVehicles：Integer，车辆种类数量。
* Speed\*：一维Double数组，车辆的行驶速度，对于所有车型默认都是1。如果不同的车型的速度不一样，会导致算子[CrossBase](../operators/CrossBase.md)、[CrossPD](../operators/CrossPD.md)以及[CrossSD](../operators/CrossSD.md)不能作用于不同车型的路径。
* ServiceTimes：一维Double数组，节点的服务时长。
* NodeTimeWindows: 一维Double列表数组，节点的服务时间窗。对于仓库来说，节点的时间窗是指车辆在仓库提货的时间窗。
* DeliveryTimeWindows: 以为Double列表数组，节点对应的货物在送货到仓库的时间窗。
* VehicleTimeWindows: 一维Double列表数组，每种车型的工作时间窗，即车辆允许离开仓库的最早时间和必须回到仓库的最晚时间。
* GroupServiceTimes\*：一维Double数组，表示节点分组对应的服务时间。假如车辆连续访问多个属于同一个分组的节点，只计算第一个节点的分组服务时间。例如，路径0(0) - 1(1) - 2(1) - 3(2) - 4(2) - 0(0)，其中阔号的数组表示节点的分组，只计算节点1和节点3的分组服务时间。
* GroupMap\*：一维Integer数组，将节点映射到其分组。
* PhysicalMap\*：一维Integer数组，将节点映射到物理节点。
* TimeMatrix：二维Double数组，行驶时间矩阵。

注意，每个节点的时间窗序列必须是递增排序。


## 返回JSON格式

```json
{
	"Name": "AdvanceTimeWindowConstraintB",
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
	+ ServiceTime：Double，服务时长。
	+ EarliestServiceTime：Double，最早服务开始时间。
	+ LatestServiceTime：Double，最晚服务开始时间。

