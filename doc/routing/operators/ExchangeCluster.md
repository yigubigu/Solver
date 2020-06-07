# ExchangeCluster

## 描述

## 调用JSON格式

```json
{
	"Name": "ExchangeCluster",
	"NumberOfNodes": 4,
	"Groups":{
		"0": 0,
		"1": 1,
		"2": 1,
		"3": 2
	},
	"Execute": [1, 2, 3]
}
```
* Name：String，算子的名称。
* NumberOfNodes: Integer，节点个数。
* Groups：一维整数数组，将节点映射到其分组。
* Execute\*：Integer列表，允许算子操作的节点集合，默认是仓库外的所有节点。

