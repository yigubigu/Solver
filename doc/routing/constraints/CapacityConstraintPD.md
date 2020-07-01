# CapacityConstraintPD

## 描述

见[CapacityConstraint](CapacityConstraint.md)。

## 调用JSON格式

```json
{
	"Name": "CapacityConstraintPD",
	"FirstPickupNode": 1,
	"NumberOfPickupNodes": 1,
	"NumberOfVehicles": 2,
	"Dimension": 2,
	"Numbers": {
		"0": 0,
		"1": 1,
		"2": -1
	},
	"Units": {
		"0": {
			"0": 1.0,
			"1": 0.5
		},
		"1": {
			"0": 1.0,
			"1": 0.5
		},
		"1": {
			"0": 1.0,
			"1": 0.5
		}
	},
	"Capacities": {
		"0": {
			"0": 100,
			"1": 200
		},
		"1": {
			"0": 100,
			"1": 400
		}
	},
	"MinimiumLoadingRate": {
		"0": 0.7,
		"1": 0.7
	},
	"Relaxable": true,
	"Coefficient": 1.0,
	"SplitOrder": true,
	"SplitVehicleType": [0, 1]
}
```
* Name: String，名称。
* FirstPickupNode: Integer，首个取货点的编号。
* NumberOfPickupNodes：Integer，取货点的数量。
* NumberOfVehicles：Integer，车辆种类数量。
* Dimension：Integer，容量的维度数量。
* Numbers：一维Integer数组，每个节点的货物件数。
* Units：二维Double数组，每个节点的货物每个维度上的单位重量。
* Capacities：二维Double数组，每种车型在每个维度上的容量。
* MinimiumLoadingRate\*：一维Double数组，每种车型的最小装载率。
* Relaxable\*：Boolean，约束是否可以进行松弛。
* Coefficient\*: Double，约束进行松弛后的惩罚系数。
* SplitOrder\*：Boolean，是否进行拆单。
* SplitVehicleType\*：Integer列表，允许进行拆单的车型。

```json
{
	"Name": "CapacityConstraint",
	"FirstPickupNode": 1,
	"NumberOfPickupNodes": 1,
	"NumberOfVehicles": 2,
	"Demands": {
		"0": 0,
		"1": 10.1,
		"2": -10.1
	},
	"Capacities": {
		"0": 100,
		"1": 200
	},
	"MinimiumLoadingRate": {
		"0": 0.7,
		"1": 0.7
	},
	"Relaxable": true,
	"Coefficient": 1.0,
	"SplitOrder": true,
	"SplitVehicleType": [0, 1]
}
```
* Demands：一维Double数组，每个节点的需求。
* Capacities：一维Double数组，每种车型的容量。

## 返回JSON格式
```json
{
	"Name": "CapacityConstraint",
	"Coefficient": 1.0,
	"Feasibility": true,
	"Cost": 0,
	"Capacity": 100,
	"Sequence":[
		{
			"ID": 0,
			"Type": "Other",
			"Number": 0,
			"Load": 0
		},
		{
			"ID": 1,
			"Type": "Pickup",
			"Number": 2,
			"Load": 10
		}
	]
}
```
* Name: String，名称。
* Coefficient：Double，约束的系数。
* Feasibility：Boolean，路径是否满足约束。
* Cost：Double，违反的惩罚成本。
* Sequence：每个节点的信息列表：
	+ ID：Integer，节点的编号。
	+ Type：String，节点的类型，有Pickup、Delivery和Other三种。
	+ Number\*: Integer，车辆载货件数。当采用第一种json格式调用时，这项存在，否则这项不存在。
	+ Load: Double，车辆的载货量。

