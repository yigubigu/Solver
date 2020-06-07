# MultiTripEnableConstraint

## 描述

## 调用JSON格式

```json
{
	"Name": "MultiTripEnableConstraint",
	"NumberOfVehicles": 2,
	"MultiTrip":{
		"0": false,
		"1": true
	}
}
```
* Name: String，名称。
* NumberOfVehicles：Integer，车辆种类数量。
* MultiTrip：一维Boolean数组，每种车型是否允许多趟。


## 返回JSON格式
```json
{
	"Name": "MultiTripEnableConstraint",
	"Coefficient": 0,
	"Feasibility": true
}
```

* Name: String，名称。
* Coefficient：Double，约束的系数。
* Feasibility：Boolean，路径是否满足约束。

