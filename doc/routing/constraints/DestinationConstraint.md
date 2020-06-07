# DestinationConstraint

## 描述

## 调用JSON格式

```json
{
	"Name": "DestinationConstraint",
	"NumberOfNodes": 4,
	"NumberOfVehicles": 2,
	"NodeMap": {
		"0": 0,
		"1": 1,
		"2": 1,
		"3": 2
	},
	"VehicleMap":{
		"0": 1,
		"1": 2
	}
}
```
* Name: String，名称。
* NumberOfNodes: Integer，节点个数。
* NumberOfVehicles：Integer，车辆种类数量。
* NodeMap：一维Integer数组，将节点映射到所在的区域。
* VehicleMap：一维Integer数组，将车辆映射到所在的区域。


## 返回JSON格式

```json
{
	"Name": "DestinationConstraint",
	"Coefficient": 1.0,
	"Feasibility": true,
	"Cost": 0,
	"District": 1
}
```

* Name: String，名称。
* Coefficient：Double，约束的系数。
* Feasibility：Boolean，路径是否满足约束。
* Cost：Double，违反的惩罚成本。
* District：Integer，车辆和节点所在区域。

