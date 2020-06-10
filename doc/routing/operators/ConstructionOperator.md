### ConstructionOperator

根据问题不同，求解器使用不同的算子，并且每次只能使用一个算子：

1. [InsertBase](InsertBase.md)：适用于常规的问题。
2. [InsertCluster](InsertCluster.md)：适用于节点分组的车辆路径问题。在这类问题中，顾客节点分为多个组，每一组有且仅有一个节点被访问。
3. [InsertElectric](InsertElectric.md)：适用于电动车路径问题（Electric Vehicle Routing Problem, EVRP）。
4. [InsertPD](InsertPD.md)：适用于取货送货问题（Pickup and Delivery Problem，PDP）。
5. [InsertSD](InsertSD.md)：适用于需求可拆分车辆路径问题（Split-Demand Vehicle Routing Problem，SDVRP）。
