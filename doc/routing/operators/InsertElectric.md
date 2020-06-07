# InsertElectric

## 描述

## 调用JSON格式

```json
{
	"Name": "InsertElectric",
	"NumberOfNodes": 5,
	"FirstChargeStation": 3,
	"ChargeStations":{
		"0":{
			"1": [3, 4],
			"2": [3, 4]
		},
		"1":{
			"0": [3, 4],
			"2": [3, 4]
		},
		"2":{
			"0": [3, 4],
			"1": [3, 4]
		}
	}
}
```
* Name：String，算子的名称。
* NumberOfNodes: Integer，节点个数。
* FirstChargeStation：Integer，第一个充电站的编号，节点FirstChargeStation至NumberOfNodes - 1都是充电站。
* ChargeStations：二维Integer列表数组，任意两个非充电站节点间允许经过的充电站。

