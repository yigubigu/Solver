# CapacityConstraintSimPD

## 描述

## 调用JSON格式


```json
{
	"Name": "CapacityConstraintSimPD",
	"NumberOfNodes": 3,
	"NumberOfVehicles": 2,
	"PickupDemands": {
		"0": 5,
		"1": 10.1,
		"2": 30.0
	},
	"DeliveryDemands": {
		"0": 2,
		"1": 2,
		"2": 1
	},
	"Capacities": {
		"0": 100,
		"1": 200
	}
}
```
* Name: String，名称。
* NumberOfNodes: Integer，节点个数。
* NumberOfVehicles：Integer，车辆种类数量。
* PickupDemands：一维Double数组，每个节点的提货需求。
* DeliveryDemands：一维Double数组，每个节点的送货需求。
* Capacities：一维Double数组，每种车型的容量。

## 返回JSON格式
```json
{
	"Name": "CapacityConstraintSimPD",
	"Coefficient": 1.0,
	"Feasibility": true,
	"Cost": 0,
	"Capacity": 100,
	"Sequence":[
		{
			"ID": 0,
			"Load": 0
		},
		{
			"ID": 1,
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
	+ "ID": Integer，节点的编号。
	+ "Load": Double，车辆的载货量。

