# MinimizeDepotDependentCost

## 描述

## 调用JSON格式

```json
{
	"Name": "MinimizeDepotDependentCost",
	"NumberOfNodes": 3,
	"NumberOfDepots": 2,
	"NumberOfVehicles": 3,
	"UnitCosts": {
		"0": {
			"0": 1.2,
			"1": 1.0
		},
		"1": {
			"0": 1.1,
			"1": 0.9
		},
		"2":{
			"0": 0.8,
			"1": 0.7
		}
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
	"Coefficient: 1
}
```
* Name: String，名称。
* NumberOfNodes: Integer，节点个数。
* NumberOfDepots：Integer，仓库数量。
* NumberOfVehicles：Integer，车辆种类数量。
* UnitCosts：二维Double数组，每种车型从每个仓库的单位行驶成本。
* PhysicalMap\*：一维Integer数组，将节点映射到物理节点。
* DistanceMatrix：二维Double数组，行驶时间矩阵。
* Coefficient\*：Double，乘到成本的系数，默认取1。


## 返回JSON格式

```json
{
	"Name": "MinimizeDepotDependentCost",
	"Coefficient": 0,
	"Feasibility": true,
	"Cost": 0,
	"Sequence":[
		{
			"ID": 0,
			"Distance": 0,
			"Cost": 0
		},
		{
			"ID": 1,
			"Distance": 10,
			"Cost": 20
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
	+ Distance：Double，到达该节点的距离。
	+ Cost：Double，到达该节点的成本。

