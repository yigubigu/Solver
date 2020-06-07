# MinimizeChargeCost

## 描述

## 调用JSON格式

```json
{
	"Name": "MinimizeChargeCost",
	"FirstChargeStation": 3,
	"ChargeCosts": 100.0,
	"Coefficient": 1
}
```
* Name: String，名称。
* FirstChargeStation：Integer，第一个充电站编号，从节点r至最后一个节点都是充电站。
* ChargeCosts：Double，每次充电成本。
* Coefficient\*：Double，乘到成本的系数，默认取1。


## 返回JSON格式

```json
{
	"Name": "MinimizeChargeCost",
	"Coefficient": 0,
	"Feasibility": true,
	"Cost": 0,
	"Sequence":[
		{
			"ID": 0,
			"IsChargeStation": false,
			"Cost": 0
		},
		{
			"ID": 1,
			"IsChargeStation": false,
			"Cost": 0
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
	+ IsChargeStation：Boolean，该节点是否是充电站。
	+ Cost：Double，到达该节点时车辆累计的充电成本。

