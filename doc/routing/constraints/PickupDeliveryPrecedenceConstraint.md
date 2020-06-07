# PickupDeliveryPrecedenceConstraint

## 描述

## 调用JSON格式

```json
{
	"Name": "PickupDeliveryPrecedenceConstraint",
	"FirstPickupNode": 1,
	"NumberOfPickupNodes": 1,
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
* PhysicalMap：一维Integer数组，将节点映射到物理节点。


## 返回JSON格式

```json
{
	"Name": "PickupDeliveryPrecedenceConstraint",
	"Coefficient": 0,
	"Feasibility": true,
	"Cost": 0,
	"Sequence":[
		{
			"ID": 0,
			"Type": "Other",
			"PhysicalLocation": 0
		},
		{
			"ID": 1,
			"Type": "Pickup",
			"PhysicalLocation": 1
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
	+ Type：String，节点的类型，有Pickup、Delivery和Other三种。
	+ PhysicalLocation：Integer，该节点对应的物理节点。

