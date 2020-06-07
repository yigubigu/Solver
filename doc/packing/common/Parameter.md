
# Parameter

## 描述

## 调用JSON格式

```json
{
	"Truck":{
		"Check": true,
		"SimpleBlock_EachNumber": 500,
		"SimpleBlock_TotalNumber": 1000,
		"ComplexBlock_LoadingRate": 0.99,
		"ComplexBlock_TotalNumber": 5000,
		"TreeSearch_SpaceSize": 2,
		"TreeSearch_BlockSize": 5,
		"TreeSearch_Depth": 2,
		"TreeSearch_LogPrint": true,
		"MultiThread": false,
		"TreeSearch_LogDetail": false,
		"TreeSearch_TimeLimt": 3600
	},
	"Tray":{
	}
}
```
* Check\*：Boolean，是否进行运行时信息校验，默认时true。
* SimpleBlock_EachNumber\*：Integer， 每种类型的SimpleBlock数量上限，默认是500。
* SimpleBlock_TotalNumber\*：Integer，总的SimpleBlock数量上限，默认是5000。
* ComplexBlock_LoadingRate\*：Double，ComplexBlock最低装载率要求，默认是0.99。
* ComplexBlock_TotalNumber\*：Integer，总的ComplexBlock数量，默认是5000。
* TreeSearch_SpaceSize\*：Integer，树搜索每层探索空间个数，默认是2。
* TreeSearch_BlockSize\*：Integer，树搜索每个空间匹配的Block数量，默认是5。
* TreeSearch_Depth\*：Integer，树搜索深度，默认是2。
* TreeSearch_LogPrint\*：Boolean，是否输出运行时信息，默认是true。
* MultiThread\*：Boolean，是否采用多线程运行，默认时false。
* TreeSearch_LogDetail\*：Boolean，是否输出详细运行时信息，默认是false。
* TreeSearch_TimeLimt\*：Integer，程序运行时间上限，默认是600000。
