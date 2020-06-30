# Data

## 描述

Data用于放置问题中会被重复使用的数据。例如，NumberOfNodes表示节点的总个数，这一项出现在大部分约束条件和算子中，因此可以在这里指定，在后续其他需要这一项的地方就可以省略。对于后续需要到数组的地方，假如该数组出现在Data，则只需要指定该数组对应的下标即可。例如，CapacityConstraint需要一个浮点型数组表示顾客的需求，假如该数组出现在*DoubleArrays*中，
```json
{
	"DoubleArrays":{
		"0":{
			"0": 0,
			"1": 1.00,
			"2": 20.0
		}
	}
}
```
则直接引用0即可
```json
{
	"CapacityConstraint":{
		"Demands": 0
	}
}
```
除此之外，Data中的数组不需要给出每一项，假如某一项没有给定，则采用java的默认值，对于整型取0，对于浮点型取0.0，对于布尔型是false。

设置Data的作用在于减少算例json的大小。例如，距离和时间矩阵往往是json中占比最大的数据项。假如同时有多组约束使用距离和时间矩阵，每一个约束都存储一份独立的距离和时间矩阵，那么整个json文件将变得很大。而通过把重复使用的表放置到Data有利于减少json文件的大小。


## 调用JSON格式

```json
{
	"NumberOfNodes": 3,
	"NumberOfVehicles": 2,
	"FirstPickupNode": 1,
	"NumberOfPickupNodes": 1,
	"IntArrays":{
		"0": {
			"Size": 2,
			"0": 1,
			"1": 2
		},
		"1": {
			"Size": 10,
			"0": 1,
			"4": 2
		}
	},
	"DoubleArrays":{},
	"BooleanArrays":{},
	"IntMatrices":{
		"0":{
			"Size": 2,
			"0": {
				"Size": 2,
				"0": 0,
				"1": 2
			},
			"1":{
				"Size": 2,
				"0": 2,
				"1": 0
			}
		},
		"1": {
			"Size": 10,
			"1": {
				"Size": 10,
				"5": 1,
				"6": 2
			}
		}
	},
	"DoubleMatrices":{},
	"BooleanMatrices":{}
}
```
* NumberOfNodes: Integer，节点个数。
* NumberOfVehicles：Integer，车型种类数目。
* FirstPickupNode: Integer，首个取货点的编号。
* NumberOfPickupNodes：Integer，取货点的数量。
* IntArrays：存放一维Integer数组的数组。
	+ Size：Integer，数组的大小。
* DoubleArrays：存放一维Double数组的数组。
* BooleanArrays：存放一维Boolean数组的数组。
* IntMatrices：存放二维Integer数组的数组。
	+ Size：Integer，数组第一维的大小。
		+ Size：Integer，数组第二维的大小。
* DoubleMatrices：存放二维Double数组的数组。
* BooleanMatrices：存放二维Boolean数组的数组。

**注意**：在Data这项里，数组的每一个维度都必须包含一个Size项表明该维度的元素的个数，而在其他地方的数组则不需要Size项。
