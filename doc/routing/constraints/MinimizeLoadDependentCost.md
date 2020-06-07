# MinimizeLoadDependentCost

## 描述

## 调用JSON格式

```json
{
	"Name": "MinimizeLoadDependentCost",
	"NumberOfNodes": 4,
	"MaxCapacity": 2,
	"Demands": {
		"0": 0,
		"1": 1,
		"2": 1,
	},
	"CostMatrix": {
		"0": {
			"0": 0,
			"1": 1.0,
			"2": 0.9
		},
		"1": {
			"0": 0,
			"1": 1.0,
			"2": 0.9
		},
		"2": {
			"0": 0,
			"1": 1.0,
			"2": 0.9
		}
	},
	"Coefficient": 1.0
}
```
* Name: String，名称。
* NumberOfNodes: Integer，节点个数。
* MaxCapacity：Integer，车辆的最大容量。
* CostMatrix：二维Double数组，每个节点在每个重量上的单位重量成本。
* Coefficient\*：Double，乘到成本的系数，默认取1。


## 返回JSON格式
```json
{
	"Name": "MinimizeLoadDependentCost",
	"Coefficient": 0,
	"Feasibility": true,
	"Cost": 0,
	"Sequence":[
		{
			"ID": 0,
			"UnitCost": 0,
			"MaxUnitCost": 0
		},
		{
			"ID": 1,
			"UnitCost": 1.0,
			"MaxUnitCost": 1.0
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
	+ UnitCost：Double，当前节点的单位成本。
	+ MaxUnitCost：Double，到达该节点所经历的节点的单位成本的最大值。

