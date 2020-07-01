# CapacityConstraint

## 描述

容量约束有2中形式。

1. 货物的基本单位是件，每一件货物允许有多维属性（例如，重量、体积等），订单的拆单操作按照件数进行。
2. 货物的属性只有一维，订单后的订单可以是任意的浮点数。


## 调用JSON格式

容量约束有2种调用的json格式
```json
{
	"Name": "CapacityConstraint",
	"NumberOfNodes": 3,
	"NumberOfVehicles": 2,
	"Dimension": 2,
	"Numbers": {
		"0": 0,
		"1": 1,
		"2": 2,
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
			"0": 0.8,
			"1": 0.7
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
* NumberOfNodes: Integer，节点个数。
* NumberOfVehicles：Integer，车辆种类数量。
* Dimension：Integer，容量的维度数量。
* Numbers：一维Integer数组，每个节点的货物件数。
* Units：二维Double数组，每个节点的货物每个维度上的单位重量。
* Capacities：二维Double数组，每种车型在每个维度上的容量。
* MinimiumLoadingRate\*：一维Double数组，每种车型的最小装载率。
* Relaxable\*：Boolean，约束是否可以进行松弛，默认取false。
* Coefficient\*: Double，约束进行松弛后的惩罚系数，默认取1。
* SplitOrder\*：Boolean，是否进行拆单，默认取false。
* SplitVehicleType\*：Integer列表，允许进行拆单的车型，默认是全部的车型。

```json
{
	"Name": "CapacityConstraint",
	"NumberOfNodes": 3,
	"NumberOfVehicles": 2,
	"Demands": {
		"0": 5,
		"1": 10.1,
		"2": 30.0
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
			"Number": 0,
			"Load": 0
		},
		{
			"ID": 1,
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
	+ ID: Integer，节点的编号。
	+ Number\*: Integer，车辆载货件数。当采用第一种json格式调用时，这项存在，否则这项不存在。
	+ Load: Double，车辆的载货量。

假如一个容量约束考虑多个维度，那么在返回结果时会也会包含多个容量约束json对象，数量和约束的维度数量一致。
