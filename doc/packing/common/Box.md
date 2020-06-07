# Box


## 描述

## 调用JSON格式

```json
[
	{
		"Node": 0,
		"Length": 100,
		"Width": 100,
		"Height": 100,
		"Number": 100,
		"Cylinder": false,
		"Tray": false,
		"Codes":["XXXXX", "YYYYY"],
		"Orients": [0, 1], 
		"Priority": 0,
		"Weights": [10.0, 10.0]
	}
]
```
* Node：Integer，物品对应的提货点编号。
* Length：Integer，物品的长度。
* Width：Integer，物品的宽度。
* Height：Integer，物品的高度。
* Number：Integer，同种类型的物品的数量。
* Cylinder\*：Boolean，物品是否是圆柱体，默认是false。
* Tray\*：Boolean，物品是否需要装托，默认是false。
* Codes：一维String数组，物品的编码，此数组大小y应等于Number，如果只包含一个编码，则默认所有的物品编码都是同一个。
* Orients\*：Integer列表，物品允许摆放的朝向列表，默认时所有的朝向都允许摆放。
  + 0：正常朝向(Length, Width, Height)
  + 1：水平旋转(Width, Length, Height)
  + 2：(Length, Height, Width)
  + 3：(Height, Length, Width)
  + 4：(Height, Width, Length)
  + 5：(Width, Height, Length)
* Priority\*：Integer，物品的优先级，默认是0。
* Weights\*：Double列表，物品各个维度的重量，默认是0。
