# MinimizeWholeVehicleCost

## 描述

## 调用JSON格式

```json
{
	"Name": "MinimizeWholeVehicleCost",
	"NumberOfNodes": 3,
	"NumberOfVehicles": 2,
	"UnitCosts": {
		"0": 1.2,
		"1": 1.0
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
	"UpperBounds":{
		"0": 0,
		"1": 100,
		"2": 300
	},
	"Coefficient: 1
}
```
* Name: String，名称。
* NumberOfNodes: Integer，节点个数。
* NumberOfVehicles：Integer，车辆种类数量。
* UnitCosts：一维Double数组，每种车型的单位行驶成本。
* PhysicalMap\*：一维Integer数组，将节点映射到物理节点。
* DistanceMatrix：二维Double数组，行驶时间矩阵。
* UpperBounds：一维Double数组，每个节点的访问成本。
* Coefficient\*：Double，乘到成本的系数，默认取1。



## 返回JSON格式

```json
{
	"Name": "MinimizeWholeVehicleCost",
	"Coefficient": 0,
	"Feasibility": true,
	"Cost": 0,
	"Sequence":[
		{
			"ID": 0,
			"Distance": 0,
			"Cost": 0,
			"UpperBound": 0
		},
		{
			"ID": 1,
			"Distance": 10,
			"Cost": 20,
			"UpperBound": 100
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
	+ UpperBound：Double，到达该节点最大的访问成本。

