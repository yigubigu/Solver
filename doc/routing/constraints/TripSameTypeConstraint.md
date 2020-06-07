# TripSameTypeConstraint

## 描述

## 调用JSON格式

```json
{
	"Name": "TripSameTypeConstraint",
	"NumberOfNodes": 3,
	"Map":{
		"0": 0,
		"1": 1,
		"2": 2
	}
}
```
* Name: String，名称。
* NumberOfNodes: Integer，节点个数。
* Map：一维Integer数组，将节点映射到其类型。


## 返回JSON格式

```json
{
	"Name": "TripSameTypeConstraint",
	"Coefficient": 0,
	"Feasibility": true,
	"Cost": 0,
	"Sequence":[
		{
			"ID": 0,
			"Type": 0
		},
		{
			"ID": 1,
			"Type": 1
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
	+ Type：Integer，节点的类型。

