# CrossDepotConstraintPD

## 描述

## 调用JSON格式

```json
{
	"Name": "CrossDepotConstraintPD",
	"FirstPickupNode": 1,
	"NumberOfPickupNodes": 3,
	"TripNumberLimit": 2,
	"Depots": [0, 1, 2]
}
```
* Name: String，名称。
* FirstPickupNode: Integer，首个取货点的编号。
* NumberOfPickupNodes：Integer，取货点的数量。
* TripNumberLimit：Integer，路径的趟数上限。
* Depots：Integer列表，物理仓库节点集合。


## 返回JSON格式

无返回

