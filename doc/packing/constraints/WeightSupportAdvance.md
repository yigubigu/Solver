# WeightSupportAdvance

## 描述

## 调用JSON格式

```json
{
	"Name": "WeightSupportAdvance",
	"Factor": 1.1,
	"Threshold": 20,
	"Map": {
		"0": {
			"Weight": 100,
			"Support": 50,
			"MaxStack": 3
		},
		"1": {
			"Weight": 100,
			"Support": 50,
			"MaxStack": 4
		},
		"2": {
			"Weight": 100,
			"Support": 10,
			"MaxStack": 1
		}
	}
}
```
* Name: String，约束名称。
* Factor：Double，两个同种类型物品A压在B上面，那么A的重量是B的重量的倍数的上限。
* Threshold：Integer，判断两个物品是否是同种类型的阈值。
* Map：一维数组，描述每个物品属性。
	+ Weight：Integer，物品的重量。
	+ Support：Integer，物品上表面支撑重量的上限。
	+ MaxStack：Integer，同种类型物品堆叠层数上限。

