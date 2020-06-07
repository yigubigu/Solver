# DistrictRestrictionConstraint

## 描述

## 调用JSON格式

```json
{
	"Name": "DistrictRestrictionConstraint",
	"NumberOfNodes": 4,
	"NodeMap":{
		"0": 0,
		"1": 1,
		"2": 1,
		"3": 2
	}
}
```
* Name: String，名称。
* NumberOfNodes: Integer，节点个数。
* NodeMap：一维Integer数组，将某个节点映射到所在区域。


## 返回JSON格式

```json
{
	"Name": "DistrictRestrictionConstraint",
	"Coefficient": 0,
	"Feasibility": true,
	"Cost": 0,
	"Sequence":[
		{
			"ID": 0,
			"District": 0
		},
		{
			"ID": 3,
			"District": 2
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
	+ District：Integer，节点所在区域。

