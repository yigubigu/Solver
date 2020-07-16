# MinimizeWeightSumCost

## 描述

## 调用JSON格式

```json
{
	"Name": "MinimizeWeightSumCost",
	"NumberOfNodes": 3,
	"NumberOfVehicles": 2,
	"Demands": {
		"0": 0,
		"1": 10,
		"2": 20,
	},
	"Units": {
		"0": 1.1,
		"1": 2.0
	},
	"LowerBounds": {
		"0": 300,
		"1": 400
	},
	"UpperBounds": {
		"0": 1000,
		"1": 2000
	},
	"Coefficient": 1,
	"Description": "minimize weight sum cost"
}
```
* Name: String，名称。
* NumberOfNodes: Integer，节点个数。
* NumberOfVehicles：Integer，车辆种类数量。
* Demands：一维Double数组，每个节点的需求。
* Units：一维Double数组，每种车型的单位重量成本。
* LowerBounds：一维Double数组，每种车型的车重下限。
* UpperBounds：一维Double数组，每种车型的车重上限。
* Coefficient\*：Double，乘到成本的系数，默认取1。
* Description\*：String，目标函数的描述，默认为空。该字符串会输出到结果中，可以用于区分目标函数集合中同名的目标函数。


## 返回JSON格式
```json
{
	"Name": "MinimizeWeightSumCost",
	"Coefficient": 1.0,
	"Feasibility": true,
	"Cost": 0,
	"Description": "minimize weight sum cost"
}
```
* Name: String，名称。
* Coefficient：Double，约束的系数。
* Feasibility：Boolean，路径是否满足约束。
* Cost：Double，违反的惩罚成本。
* Description\*：String，目标函数的描述。

