# VisitRestrictionConstraint

## 描述

## 调用JSON格式

```json
{
	"Name": "VisitRestrictionConstraint",
	"NumberOfNodes": 3,
	"NumberOfVehicles": 2,
	"FeasibilityMatrix":{ 
		"0":{
			"0": true,
			"1": true,
			"2": false
		},
		"1":{
			"0": true,
			"1": false,
			"2": true
		}
	}
}
```
* Name: String，名称。
* NumberOfNodes: Integer，节点个数。
* NumberOfVehicles：Integer，车辆种类数量。
* FeasibilityMatrix：二维Boolean数组，某种车型是否可以访问某个节点。


## 返回JSON格式

```json
{
	"Name": "VisitRestrictionConstraint",
	"Coefficient": 0,
	"Feasibility": true,
	"Cost": 0,
	"Sequence":[
		{
			"ID": 0,
			"Permit": true
		},
		{
			"ID": 1,
			"Permit": true
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
	+ Permit：Boolean，车辆是否允许访问该节点。

