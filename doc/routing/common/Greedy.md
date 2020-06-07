# Greedy

## 描述


## 调用JSON格式

```json
{
	"NumberOfVehicles": 2,
	"NumberOfVehicleEachType":{
		"0": 10,
		"1": 10
	},
	"Vehicles":[
		{
			"Depot": 0,
			"NumberOfTypes": 2,
			"Types":[
				0,
				1
			],
			"NumberOfEachType":[
				10,
				10
			]
		}
	],
	"NumberOfNodes": 100,
	"PhysicalMap": {},
	"DistanceMatrix": {}
}
```
* NumberOfVehicles：Integer，车辆类型数量。
* NumberOfVehicleEachType\*：一维整数数组，给出每种车型可用车辆数量上限，默认是正无穷。
* Vehicles: List，列举每个仓库可用车辆数量情况。
* Depot：Integer，仓库的节点编号。
* NumberOfTypes：Integer，可用的车型数量。
* Types：Integer列表，列举该仓库可用的车型。
* NumberOfEachType：Integer列表，列举该仓库每种车型的可用车辆数量上限。
* NumberOfNodes\*：Integer，节点个数。
* PhysicalMap\*：一维Integer数组，节点到物理节点的映射。
* DistanceMatrix\*：二维Double数组，距离矩阵。


其中，后面三项NumberOfNodes、PhysicalMap和DistanceMatrix在仓库只有一个的情况下可以省略。
