# PhysicalNodeNumberConstraintPD

## 描述

## 调用JSON格式

```json
{
	"Name": "PhysicalNodeNumberConstraintPD",
	"FirstPickupNode": 1,
	"NumberOfPickupNodes": 1,
	"NumberOfVehicles": 2,
	"Limits": {
		"0": 10,
		"1": 20
	},
	"PhysicalMap":{
		"0": 0,
		"1": 1,
		"2": 2
	}
}
```
* Name: String，名称。
* FirstPickupNode: Integer，首个取货点的编号。
* NumberOfPickupNodes：Integer，取货点的数量。
* NumberOfVehicles：Integer，车辆种类数量。
* Limits：一维Integer数组，每种车型的每一趟经过的物理节点数量上限。
* PhysicalMap：一维Integer数组，将节点映射到物理节点。


## 返回JSON格式

```json
{
	"Name": "PhysicalNodeNumberConstraintPD",
	"Coefficient": 0,
	"Feasibility": true,
	"Cost": 0,
	"Sequence":[
		{
			"ID": 0,
			"PhysicalNode": 0
		},
		{
			"ID": 1,
			"PhysicalNode": 1
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
	+ PhysicalNode：Integer，该节点对应的物理节点。

