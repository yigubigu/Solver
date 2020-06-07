# DepotVisitConstraint

## 描述

## 调用JSON格式

```json
{
	"Name": "DepotVisitConstraint",
	"NumberOfNodes": 4,
	"NumberOfDepots": 2,
	"VisitLimit": {
		"0": [ 1, 2],
		"1": [3, 4]
	}
}
```
* Name: String，名称。
* NumberOfNodes: Integer，节点个数。
* NumberOfDepots：Integer，仓库数量。
* VisitLimit：一维Integer列表数组，每个仓库出发的车辆允许访问的节点。


## 返回JSON格式

无返回

