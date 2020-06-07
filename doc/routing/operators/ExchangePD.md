# ExchangePD

## 描述

## 调用JSON格式

```json
{
	"Name": "ExchangePD",
	"FirstPickupNode": 1,
	"NumberOfPickupNodes": 1,
	"Execute": [1, 2, 3]
}
```
* Name：String，算子的名称。
* FirstPickupNode: Integer，首个取货点的编号。
* NumberOfPickupNodes：Integer，取货点的数量。
* Execute\*：Integer列表，允许算子操作的节点集合，默认是仓库外的所有节点。

