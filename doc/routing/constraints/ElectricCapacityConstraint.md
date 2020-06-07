# ElectricCapacityConstraint

## 描述

## 调用JSON格式

```json
{
	"Name": "ElectricCapacityConstraint",
	"NumberOfNodes": 4,
	"NumberOfVehicles": 2,
	"FirstChargeStation": 3,
	"Capacities": {
		"0": 100,
		"1": 200
	},
	"PhysicalMap":{
		"0": 0,
		"1": 1,
		"2": 2
	},
	"DistanceMatrix":{ 
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
	},
	"Relaxable": true,
	"Coefficient": 100
}
```
* Name: String，名称。
* NumberOfNodes: Integer，节点个数。
* NumberOfVehicles：Integer，车辆种类数量。
* FirstChargeStation：Integer，第一个充电站编号，从节点r至节点NumberOfNodes - 1都是充电站。
* Capacities：一维Double数组，每种车型充满电后最长行驶距离。
* PhysicalMap\*：一维Integer数组，将节点映射到物理节点。
* DistanceMatrix：二维Double数组，行驶时间矩阵。
* Relaxable\*：Boolean，约束是否允许松弛。
* Coefficient\*：Double，约束松弛后的惩罚系数。


## 返回JSON格式

```json
{
	"Name": "ElectricCapacityConstraint",
	"Coefficient": 0,
	"Feasibility": true,
	"Cost": 0,
	"Sequence":[
		{
			"ID": 0,
			"IsChargeStation": false,
			"RemainCapacity": 100
		},
		{
			"ID": 1,
			"IsChargeStation": false,
			"RemainCapacity": 80
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
	+ IsChargeStation：Boolean，该节点是否是充电站。
	+ RemainCapacity：Double，到达该节点时车辆剩余的电量可以行驶的最长距离。

