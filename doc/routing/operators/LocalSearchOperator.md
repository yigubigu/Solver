# LocalSearchOperator

求解器内置以下邻域搜索算子：

1. [RelocateBase](RelocateBase.md)：将一个节点移动到另一条路径，适用于一般的问题。
2. [RelocateBaseIntra](RelocateBaseIntra.md)：将一个节点移动到同一条路径不同的位置，适用于一般的问题。
3. [RelocateCluster](RelocateCluster.md)：将一个节点移动到另一条路径，适用于分组车辆路径问题。
4. [RelocatePD](RelocatePD.md)：将一个节点移动到另一条路径，适用于取货送货问题。
5. [RelocateSD](RelocateSD.md)：将一个节点移动到另一条路径，适用于需求可拆分车辆路径问题。
6. [ExchangeBase](ExchangeBase.md)：交换两条路径上的两个节点，适用于一般的车辆路径问题。
7. [ExchangeBaseDeep](ExchangeBaseDeep.md)：交换两条路径上的两个节点，适用于一般的车辆路径问题，搜索范围比ExchangeBase广和耗时。
8. [ExchangeCluster](ExchangeCluster.md)：交换两条路径上的两个节点，适用于分组车辆路径问题。
9. [ExchangeClusterDeep](ExchangeClusterDeep.md)：交换两条路径上的两个节点，适用于一般的车辆路径问题，搜索范围比ExchangeCluster广和耗时。
10. [ExchangePD](ExchangePD.md)：交换两条路径上的两个节点，适用于取货送货问题。
11. [ExchangeSD](ExchangeSD.md)：交换两条路径上的两个节点，适用于需求可拆分车辆路径问题。
12. [CrossBase](CrossBase.md)：交换两条路径上的两条边，适用于一般的车辆路径问题和分组车辆路径问题。
13. [CrossPD](CrossPD.md)：交换两条路径上的两条边，适用于取货送货问题。
14. [CrossSD](CrossSD.md)：交换两条路径上的两条边，适用于需求可拆分车辆路径问题。


算子之间一般配合配合着使用：

1. 对于中小规模一般的车辆路径问题，选用RelocateBase、RelocateBaseIntra、ExchangeBaseDeep和CrossBase。
2. 对于大规模一般的车辆路径问题，选用RelocateBase、ExchangeBase和CrossBase。
3. 对于中小规模分组的车辆路径问题，选用RelocateCluster、RelocateBaseIntra、ExchangeClusterDeep和CrossBase。
4. 对于大规模分组的车辆路径问题，选用RelocateCluster、ExchangeCluster和CrossBase。
5. 对于取货送货问题，选用RelocatePD、ExchangePD和CrossPD。
6. 对于需求可拆分车辆路径问题，选用RelocateSD、ExchangeSD和CrossSD。
