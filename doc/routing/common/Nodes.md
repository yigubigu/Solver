# Nodes

## 描述

## 调用JSON格式

```json
{
	"Customers":[
		1,
		2,
		3
	],
	"Demands":
	{
		"1": 10,
		"2": 20,
		"3": 10
	},
	"Priorities":
	{
		"1": 100,
		"2": 10,
		"3": 1
	}
}
```
* Customers：Integer列表，需要插入的节点序列。
* Demands\*：Double列表，节点的需求，只有当问题是需求可拆分问题时才需要指定，其他问题可以省略。
* Priorities\*：一维Integer数组，节点的优先级，数值越高，越早考虑插入到解中，可以省略，默认所有节点的优先级是一样的。
