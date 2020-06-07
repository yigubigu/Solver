# PhysicalArcNumberConstraint

## 描述

## 调用JSON格式

```json
{
	"Name": "PhysicalArcNumberConstraint",
	"NumberOfNodes": 3,
	"NumberOfVehicles": 2,
	"Limits": {
		"0": 10,
		"1": 5
	},
	"PhysicalMap":{
		"0": 0,
		"1": 1,
		"2": 2
	}
}
```
* Name: String，名称。
* NumberOfNodes: Integer，节点个数。
* NumberOfVehicles：Integer，车辆种类数量。
* Limits：Integer，每种车型的在每一趟经过的物理边的上限。
* PhysicalMap：一维Integer数组，将节点映射到物理节点。


## 返回JSON格式

```json
{
	"Name": "PhysicalArcNumberConstraint",
	"Coefficient": 0,
	"Feasibility": true,
	"Cost": 0,
	"Sequence":[
		{
			"ID": 0,
			"Number": 0
		},
		{
			"ID": 1,
			"Number": 1
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
	+ Number：Integer，到达该节点的经过的物理边数量。

