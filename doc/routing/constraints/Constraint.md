# Constraint

目前求解器已经集成的约束条件包括：

 1. [CapacityConstraint](CapacityConstraint.md)<sup>Ⓜ</sup>：容量约束。
 2. [CapacityConstraintPD](CapacityConstraintPD.md)<sup>Ⓜ</sup>：取货送货问题（Pickup and Delivery）的容量约束。
 3. [TimeWindowConstraint](TimeWindowConstraint.md)<sup>Ⓜ</sup>：时间窗约束。
 4. [GeneralTimeWindowConstraint](GeneralTimeWindowConstraint.md)<sup>Ⓜ</sup>：通用时间窗约束，允许顾客节点有多个服务时间窗、仓库有多个提货时间窗、不同的车型有不同的工作时间窗和行驶速度。
 5. [TimeWindowConstraintPD](TimeWindowConstraintPD.md)<sup>Ⓜ</sup>：取货送货问题的时间窗约束。
 6. TimeWindowConstraintTD<sup>Ⓜ</sup>：考虑车辆行驶时间可变（Time Dependent Travel Time）的时间窗约束，两点i和j之间的行驶时间t<sub>i,j</sub>(a)是车辆从i离开的时间a的分段线性函数，并且满足先进先出（FIFO）规则。
 7. [SoftTimeWindowConstraint](SoftTimeWindowConstraint.md)<sup>Ⓜ</sup>：软时间窗约束，车辆早到或晚到都会被惩罚，而且车辆不能在顾客处等待。
 8. [SoftTimeWindowConstraintPD](SoftTimeWindowConstraintPD.md)<sup>Ⓜ</sup>：取货送货问题的软时间约束。
 9. TimeWindowWaitConstraintPD<sup>Ⓜ</sup>：针对取货送货问题，车辆到达一个点时需要考虑一个服务的等待时间。假如车辆连续经过多个点都对应同一个物理点，那么只需要在第一个点考虑等待时间。该约束的应用场景类似快递配送，快递员到达一个地点后打电话通知多个顾客到约定地点取货，从打电话到顾客来取件的时间就对应服务等待时间。
 10. [TimeWindowConstraintLoad](TimeWindowConstraintLoad.md)：考虑装货时间的时间窗约束，车辆在出发前需要将配送的货物装车，而装货时间是货量的一个线性函数。同时，装货的设备（包括人工）假如足够多，每辆车之间装车操作相对独立。
 11. TimeWindowQueueConstraint：考虑货物加工时间的时间窗约束，货物在装车前都需要进行加工，每个顾客的货物加工时间固定，加工的设备只有一台，所以车辆有可能由于需要等待加工的货物装车而发生排队的情况。
 12. TimeWindowQueueReleaseConstraint：考虑货物开始时间和加工时间的时间窗约束，是 TimeWindowQueueConstraint的通用版本。在该约束中，货物有一个允许开始加工时间（Release time），在规划货物加工顺序的时候需要考虑货物的允许开始加工时间。
 13. [CrossDepotConstraintPD](CrossDepotConstraintPD.md)：节点中的某些节点对应实际的物理仓库，车辆从物理仓库出发就算一趟，而车辆行驶的趟数不能超过给定的限制。
 14. [DepotVisitConstraint](DepotVisitConstraint.md)<sup>Ⓜ</sup>：在该约束中，从某个仓库出发的车辆只允许访问某些节点。
 15. [DestinationConstraint](DestinationConstraint.md)：车辆和顾客都属于某个区域，车辆服务的最后一个顾客必须和车辆属于同一个区域。
 16. [DistrictRestrictionConstraint](DistrictRestrictionConstraint.md)<sup>Ⓜ</sup>：车辆区域访问限制约束，即车辆不允许跨区运输。
 17. [DurationConstraint](DurationConstraint.md)<sup>Ⓜ</sup>：工作时长约束，即车辆的从仓库出发到回到仓库的时长不能超过给定的限制。
 18. [DurationConstraintPD](DurationConstraintPD.md)<sup>Ⓜ</sup>：取货送货问题的工作时长约束。
 19. [ElectricCapacityConstraint](ElectricCapacityConstraint.md)<sup>Ⓜ</sup>：电动车行驶里程约束，即电动车由于电池容量有限，一次充电后行驶的里程不能超过给定的限制，中途允许到充电站充电，每一次充电要求必须充满，并且充电时长是一个定值。
 20. [PhysicalArcNumberConstraint](PhysicalArcNumberConstraint.md)<sup>Ⓜ</sup>：车辆每一趟经过的物理边（即两个点在物理上不是同一个地方）的次数不能超过给定限制。
 21. [PhysicalNodeNumberConstraintPD](PhysicalNodeNumberConstraintPD.md)：针对取货送货问题，车辆每一趟经过的物理点的次数不能超过给定限制。
 22. [PickupDeliveryPrecedenceConstraint](PickupDeliveryPrecedenceConstraint.md)<sup>Ⓜ</sup>：针对取货送货问题，车辆多个连续访问的节点对应同一个物理节点，那么卸货点必须在取货点先访问，对应到同一个地方先卸货后取货。
 23. [VisitRestrictionConstraint](VisitRestrictionConstraint.md)<sup>Ⓜ</sup>：车辆访问节点约束，即限定某些节点只能被特定车型访问。
 24. [VisitRestrictionConstraintPD](VisitRestrictionConstraintPD.md)<sup>Ⓜ</sup>：取货送货问题的车辆访问节点约束。
 25. [TripSameTypeConstraint](TripSameTypeConstraint.md)<sup>Ⓜ</sup>：车辆的每一趟访问的节点必须属于同一种类型。
 26. [MultiTripEnableConstraint](MultiTripEnableConstraint.md)<sup>Ⓜ</sup>：只允许某些特定的车型执行多趟运输（Multi-Trip）。
 27. [DistancePruneConstraint](DistancePruneConstraint.md)<sup>Ⓜ</sup>：没有实际意义，作用是加速邻域搜索速度。
 28. DistancePruneConstraintPD<sup>Ⓜ</sup>：取货送货问题，没有实际意义，作用是加速邻域搜索速度。
 29. PackingConstraint<sup>Ⓜ</sup>：三维装载约束，通过该约束可以将车辆路径问题和三维装箱问题结合在一起。

目前求解器已经集成的目标函数包括：

 1. [MinimizeDistance](MinimizeDistance.md)<sup>Ⓜ</sup>：最小化车辆的行驶距离成本。
 2. [MinimizeDistancePD](MinimizeDistancePD.md)<sup>Ⓜ</sup>：针对取货送货问题，最小化车辆的行驶距离成本。
 3. [MinimizeFixedCost](MinimizeFixedCost.md)<sup>Ⓜ</sup>：最小化车辆的固定成本。
 4. [MinimizeFixedCostPD](MinimizeFixedCostPD.md)<sup>Ⓜ</sup>：针对取货送货问题，最小化车辆的固定成本。
 5. [MaximizeProfit](MaximizeProfit.md)<sup>Ⓜ</sup>：最大化节点的访问收益，每一个节点都有一个收益，访问该节点即可以获取该收益。
 6. [MaximizeProfitPD](MaximizeProfitPD.md)<sup>Ⓜ</sup>：针对取货送货问题，最大化节点访问收益。
 7. [MinimizeChargeCost](MinimizeChargeCost.md)<sup>Ⓜ</sup>：在电动车路径问题中，最小化充电成本，车辆每访问以此充电站即需要支付一个固定数量的成本。
 8. MinimizeClusterCost<sup>Ⓜ</sup>：最小化路径上任意两个节点的欧氏距离平方之和，目的是尽可能让同一条路径上的点聚集在一起。
 9. [MinimizeCrossPenalty](MinimizeCrossPenalty.md)：最小化车辆跨区访问的成本，车辆一旦跨区，跨区成本是车辆的行驶里程，否则，跨区成本为0。
 10. [MinimizeDepotDependentCost](MinimizeDepotDependentCost.md)<sup>Ⓜ</sup>：最小化车辆行驶距离成本，不同仓库出发的车辆的单位行驶成本有所不同。
 11. MinimizeDepotPairCost<sup>Ⓜ</sup>：最小化车辆访问节点的成本，车辆从某一个仓库出发访问一个节点需要支付一个成本，不同的仓库出发的车辆访问同一个节点的成本有所不同。
 12. [MinimizeLoadDependentCost](MinimizeLoadDependentCost.md)<sup>Ⓜ</sup>：路径成本和车辆载货量相关。给定路径(0, 1, 2, ..., n, 0)，假定c\[\]\[\]是成本矩阵，q是车辆的载货量，那么路径成本是q * max<sub>i = 1,...,n</sub>c\[i\]\[q\]。
 13. MinimizeStartEndCost：用于服务网络规划问题（Service Network Design Problem），表示从终点返回起点的成本。
 14. [MinimizeTypeSumCost](MinimizeTypeSumCost.md)<sup>Ⓜ</sup>：车辆经过的顾客的需求可以分为不同的种类，每种类型的需求单位成本不一样，路径总成本是所有类型的需求成本之和（单位成本 * 需求量）。
 15. [MinimizeWeightSumCost](MinimizeWeightSumCost.md)：用q表示车中，u表示单位重量成本，mq表示一个常数，那么路径的成本是u * max(q, mq)。
 16. [MinimizeWholeVehicleCost](MinimizeWholeVehicleCost.md)：用d表示路径的距离，u表示单位行驶成本，ub表示零担成本，那么路径的成本是min(u * d, ub)。
 17. MinimizeDepotBalanceCost<sup>Ⓜ</sup>：顾客的订单来自于不同的仓库，当配送车辆出发的仓库和订单仓库不一致时，需要首先将订单运输到发车的仓库，也就是需要在两个仓库之间建立连接，这个连接的建立只需要支付一次性固定成本。
 18. MinimizeInventoryCost<sup>Ⓜ</sup>：最小化节点的库存成本，节点有一个库存成本，等于（最晚开始时间-送达时间）* 系数。该目标函数一般用于排产问题。

注：Ⓜ表示支持多趟（Multi-Trip）的约束条件或目标函数。

以MinimizeDistance为例，介绍约束条件和目标函数的json结构。假如Data项不存在，则json内容如下：
```json
{
	"Name": "MinimizeDistance",
	"NumberOfNodes": 3,
	"NumberOfVehicles": 2,
	"UnitCosts":{
		"0": 1.0,
		"1": 2.0
	},
	"DistanceMatrix":{ 
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
	"Coefficient: 1
}
```
* Name：String，约束的名称。
* NumberOfNodes：Integer，节点的数量。
* NumberOfVehicles：Integer，车型种类数量。
* UnitCosts：一维Double数组，每种车型的单位行驶成本。
* DistanceMatrix：二维Double数组，距离矩阵。
* Coefficient\*：Double，乘到成本的系数（带\*表示该项目可以省略）。


假如NumberOfNodes、NumberOfVehicles和DistanceMatrix都在Data项里定义，则该目标函数的json可以简化为
 ```json
{
	"Name": "MinimizeDistance",
	"UnitCosts":{
		"0": 1.0,
		"1": 2.0
	},
	"DistanceMatrix": 0
}
```
其中``"DistanceMatrix": 0``表示距离矩阵是Data中的DoubleMatrices的第一个矩阵。假如算例中很多节点对应的物理节点都是同一个，那么可以在json里指定节点到物理节点的映射，然后DistanceMatrix使用物理节点的距离矩阵。
 ```json
{
	"Name": "MinimizeDistance",
	"NumberOfNodes": 3,
	"NumberOfVehicles": 2,
	"UnitCosts": {},
	"PhysicalMap":{
		"0": 0,
		"1": 1,
		"2": 1
	},
	"DistanceMatrix": {}
}
```
* PhysicalMap\*：一维Integer数组，将一个节点映射到其物理节点。
