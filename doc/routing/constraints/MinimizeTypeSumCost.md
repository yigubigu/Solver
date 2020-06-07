# MinimizeTypeSumCost

## 描述

## 调用JSON格式

```json
{
	"Name": "MinimizeTypeSumCost",
	"NumberOfNodes": 3,
	"NumberOfVehicles": 2,
	"NumberOfTypes": 2,
	"Demands": {
		"0": 0,
		"1": 10,
		"2": 20,
	},
	"TypeMap":{
		"0": 0,
		"1": 1,
		"2": 2
	},
	"Units":{
		"0": {
			"0": 0,
			"1": 1.0,
			"2": 0.9
		},
		"1": {
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
* NumberOfVehicles：Integer，车辆种类数量。
* NumberOfTypes：Integer，节点的种类数量。
* Demands：一维Double数组，每个节点的需求。
* TypeMap：一维Integer数组，将每个节点映射到其类型。
* Units：二维Double数组，每种车型访问某种类型的节点的单位重量成本。
* Coefficient\*：Double，乘到成本的系数，默认取1。


## 返回JSON格式
```json
{
	"Name": "MinimizeTypeSumCost",
	"Coefficient": 0,
	"Feasibility": true,
	"Cost": 0,
	"TypeCost":{
		"0": 100,
		"1": 100
	}
}
```

* Name: String，名称。
* Coefficient：Double，约束的系数。
* Feasibility：Boolean，路径是否满足约束。
* Cost：Double，违反的惩罚成本。
* TypeCost：一维Double数组，每种类型的访问成本。

