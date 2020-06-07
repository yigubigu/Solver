# MaximizeProfitPD

## 描述

## 调用JSON格式

```json
{
	"Name": "MaximizeProfitPD",
	"NumberOfNodes": 3,
	"NumberOfVehicles": 2,
	"ProfitMatrix":{
		"0":{
			"0": 0.0,
			"1": 1.0,
			"2": 2.0
		},
		"1":{
			"0": 1.0,
			"1": 0.0,
			"2": 1.0
		}
	},
	"Coefficient": 1
}
```
* Name: String，名称。
* NumberOfNodes: Integer，节点个数。
* NumberOfVehicles：Integer，车辆种类数量。
* MaximizeProfit：二维Double数组，每种车型访问每一个节点获得收益。
* Coefficient\*：Double，乘到目标函数的系数，默认取1。


## 返回JSON格式

```json
{
	"Name": "MaximizeProfitPD",
	"Coefficient": 0,
	"Feasibility": true,
	"Cost": 0,
	"Sequence":[
		{
			"ID": 0,
			"Profit": 0
		},
		{
			"ID": 1,
			"Profit": 80
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
	+ Profit：Double，到达该节点时车辆总共获得的收益。

