# PackingConstraint

## 描述

## 调用JSON格式


```json
{
	"Name": "PackingConstraint",
	"Data": {
		"Parameter": {},
		"Box": {},
		"Bin": {},
		"Tray": {},
		"Constraint": {},
		"BlockSortingRule": {}
	}
}
```
* Name: String，名称。
* Data: HashMap，装箱相关的问题数据，每一项的介绍在[这里](../../../README.md#装箱问题)。

## 返回JSON格式
```json
{
	"Name": "PackingConstraint",
	"Coefficient": 1.0,
	"Feasibility": true,
	"Cost": 0,
	"Solution":{
		"LoadingRate": 0.8,
		"NumberOfBins": 1,
		"Bins":[]
	}
}
```
* Name: String，名称。
* Coefficient：Double，约束的系数。
* Feasibility：Boolean，路径是否满足约束。
* Cost：Double，违反的惩罚成本。
* Solution：HashMap，路径的装箱方案。
	+ "LoadingRate": Double，车辆的装载率。
	+ "NumberOfBins": Integer，装箱方案的数量。在多趟（Multi-Trip）的场景里，每一趟对应一个装箱方案。
	+ Bins：HashMap列表，每一个装箱方案的详细介绍，具体格式在[这里](../../packing/common/Result.md)。

