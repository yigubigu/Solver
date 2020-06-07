# Result

## 描述

## 调用JSON格式

```json
{
	"Cost": 100.0,
	"Feasibility": true,
	"NumberOfRoutes": 1,
	"Unassign":[
		{
			"ID": 6,
			"Reason": "TIME_WINDOW_CONSTRAINT"
		}
	],
	"Routes":[
		{
			"Type": 0,
			"Cost": 100,
			"Feasibility": true,
			"NumberOfNodes": 5,
			"Sequence": [0, 1, 2, 3, 0],
			"Constraints":[
				{
					"Name": "TimeWindowConstraint",
					"Coefficient": 0,
					"Feasibility": true,
					"Cost": 0,
					"Sequence":[
						{
							"ID": 0,
							"Arrive": 0,
							"Leave": 0,
							"ServiceTime": 0,
							"EarliestServiceTime": 0,
							"LatestServiceTime": 1000
						}
					]
				}
			]
		}
	]
}
```
* Cost：Double，解的成本。
* Feasibility：Boolean，解的合法性。
* NumberOfRoutes：Integer，路径的数量。
* Unassign：没能服务的节点列表。
  + ID：Integer，节点编号。
  + Reason：String，不能被服务的原因。
* Routes：路径列表。
  + Type：Integer，车辆类型。
  + Cost：Double，路径的成本。
  + Feasibility：Boolean，路径的合法性。
  + NumberOfNodes：路径节点的数量（包括仓库）。
  + Sequence：Integer列表，路径经过的节点序列。
  + Constraints：路径约束的属性列表。
     - Name：String，约束名称。
	 - Coefficient：Double，约束松弛的惩罚系数。
	 - Feasibility：Boolean，约束的合法性。
	 - Cost：Double，约束的成本。
	 - Sequence：每个节点关于这个约束的属性。
	   + ID：Integer，节点的编号。
	   + Arrive：Double，到达时间。
	   + Leave：Double，离开时间。
	   + ServiceTime：Double，服务时长。
	   + EarliestServiceTime：Double，最早服务开始时间。
	   + LatestServiceTime：Double，最晚服务开始时间。


其中，路径中的Constraints项主要输出的是有助于解析结果的信息，不同的约束输出的结果是不同的。
