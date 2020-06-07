# DurationConstraintPD

## 描述

## 调用JSON格式

```json
{
	"Name": "DurationConstraintPD",
	"FirstPickupNode": 1,
	"NumberOfPickupNodes": 1,
	"NumberOfVehicles": 2,
	"Speed": {
		"0": 1.5,
		"1": 1
	},
	"Durations":{
		"0": 1000,
		"1": 2000,
	},
	"ServiceTimes":{
		"0": 0,
		"1": 10,
		"2": 10
	},
	"PhysicalMap":{
		"0": 0,
		"1": 1,
		"2": 2
	},
	"TimeMatrix":{ 
		"0":{
			"0": 0.0,
			"1": 1.0,
			"2": 2.0
		},
		"1":{
			"0": 1.0,
			"1": 0.0,
			"2": 1.0
		},
		"2":{
			"0": 2.0,
			"1": 1.0,
			"2": 0.0
		}
	},
	"Relaxable": true,
	"Coefficient": 1.0
}
```
* Name: String，名称。
* FirstPickupNode: Integer，首个取货点的编号。
* NumberOfPickupNodes：Integer，取货点的数量。
* NumberOfVehicles：Integer，车辆种类数量。
* Speed\*：一维Double数组，车辆的行驶速度。
* Durations：一维Double数组，车辆的工作时长。
* ServiceTimes：一维Double数组，节点的服务时长。
* PhysicalMap\*：一维Integer数组，将节点映射到物理节点。
* TimeMatrix：二维Double数组，行驶时间矩阵。
* Relaxable\*：Boolean，约束是否可以进行松弛。
* Coefficient\*: Double，约束进行松弛后的惩罚系数。


## 返回JSON格式

```json
{
	"Name": "DurationConstraintPD",
	"Coefficient": 0,
	"Feasibility": true,
	"Cost": 0,
	"Sequence":[
		{
			"ID": 0,
			"Arrive": 0,
			"Leave": 0,
			"ServiceTime": 0,
			"Type": "Other"
		},
		{
			"ID": 1,
			"Arrive": 10,
			"Leave": 20,
			"ServiceTime": 10,
			"Type": "Pickup"
		}
	]
}
```

* Name: String，名称。
* Coefficient：Double，约束的系数。
* Feasibility：Boolean，路径是否满足约束。
* Cost：Double，违反的惩罚成本。
* Sequence：每个节点关于这个约束的属性。
	+ ID：Integer，节点的编号。
	+ Arrive：Double，到达时间。
	+ Leave：Double，离开时间。
	+  ServiceTime：Double，服务时长。
	+ Type：String，节点的类型，有Pickup、Delivery和Other三种。

