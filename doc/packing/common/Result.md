# Result

## 描述

## 调用JSON格式

```json
{
	"LoadingRate": 0.11,
	"NumberOfBins": 1,
	"Bins":[
		{
			"Volume": 8035200.0,
			"Bin":{
				"Length": 1203,
				"Height": 239,
				"Width": 235
			},
			"Item":[
				{
					"Order": 1,
					"Cylinder": false,
					"Tray": 0,
					"Orient": 0,
					"Position":{
						"X": 0,
						"Y": 0,
						"Z": 0
					},
					"Priority": 1,
					"Node": 0,
					"Code": "Tray1",
					"OriginCuboid":{
						"Length": 120,
						"Height": 93,
						"Width": 80
					},
					"PlaceCuboid":{
						"Length": 120,
						"Height": 93,
						"Width": 80
					}
				}
			],
			"Tray":[
				{
					"Volume": 709776.0,
					"Bin": {
						"Length": 120,
						"Height": 239,
						"Width": 80
					},
					"Items": []
				}
			]
		}
	]
}
```
* LoadingRate：Double，整体物品的装载率。
* NumberOfBins：Integer，箱子的数量。
* Bins：每个箱子的装载情况列表。
  + Volume：Double，箱子内物品的体积之和。
  + Bin：箱子的信息：
    - Length：Integer，箱子的长度。
	- Height：Integer，箱子的宽度。
	- Width：Integer，箱子的高度。
 + Item：箱内每个物品的情况。
 	- Order：Integer，装箱次序。
	- Cylinder：Boolean，物品是否是圆柱体。
	- Tray：Integer，当物品实际是一个托盘时，纸箱托盘数组下标。
	- Orient：Integer，物品的朝向。
	- Position：物品左下角的坐标。
		+ X：Integer，X轴坐标。
		+ Y：Integer，Y轴坐标。
		+ Z：Integer，Z轴坐标。
	- Priority：Integer，物品的优先级。
	- Node：Integer，物品所在的提货点编号。
	- Code：String，物品的编码。
	- OriginCuboid：物品原始的三维信息。
		+ Length：Integer，长度。
		+ Height：Integer，高度。
		+ Width：Integer，宽度。
	- PlaceCuboid：按当前朝向摆放后的三维信息。
		+ Length：Integer，长度。
		+ Height：Integer，高度。
		+ Width：Integer，宽度。
 + Tray：箱向内托盘的摆放情况。
	 - Volume：Double，托盘内物品体积之和。
		 + Length：Integer，托盘的长度。
		 + Height：Integer，托盘的高度+物品堆叠的高度。
		 + Width：Integer，托盘的宽度
	 - Items：托盘内物品摆放情况列表，同箱内物品的json定义。
