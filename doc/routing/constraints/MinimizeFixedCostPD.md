# MinimizeFixedCostPD

## 描述

## 调用JSON格式

```json
{
	"Name": "MinimizeFixedCostPD",
	"NumberOfVehicles": 2,
	"FixCosts": {
		"0": 100,
		"1": 200
	},
	"Coefficient: 1
}
```
* Name: String，名称。
* NumberOfVehicles：Integer，车辆种类数量。
* FixCosts：一维Double数组，每种车型的固定成本。
* Coefficient\*：Double，乘到成本的系数，默认取1。


## 返回JSON格式

```json
{
	"Name": "MinimizeFixedCostPD",
	"Coefficient": 0,
	"Feasibility": true,
	"Cost": 100,
	"Fix": 100
}
```

* Name: String，名称。
* Coefficient：Double，约束的系数。
* Feasibility：Boolean，路径是否满足约束。
* Cost：Double，违反的惩罚成本。
* Fix：Double，车辆的固定成本。

