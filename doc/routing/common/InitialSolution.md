# InitialSolution

## 描述

## 调用JSON格式
```json
{
	"Type": "Base",
	"Routes":[
		{
			"Type": 0,
			"Sequence":[
				0,
				1,
				2,
				0
			]
		}
	]
}
```
* Type：String，解的类型，包括Base和PickupDelivery。Base对应一般的问题（包括分组车辆路径问题），PickupDelivery则对应取货送货问题。目前暂不支持需求可拆分问题提供初始解。
* Routes：List，路径列表。
  + Type\*: Integer，路径的类型。假如问题只有一种类型的车辆，该项可以省略，默认值时-1。
  + Sequence：Integer列表，路径的节点序列。
