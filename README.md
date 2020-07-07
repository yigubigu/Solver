# 车辆路径和装箱求解器

车辆路径和装箱求解器有南京大学[罗志兴](https://sme.nju.edu.cn/lzx/list.htm)副教授带领团队开发，可以用于求解常见的车辆路路径问题和三维装箱问题以及这两个问题的结合。在保障高效的性能同时，求解器提供丰富的接口方便用户实现自定义的约束条件和目标函数，做到了性能、通用性、拓展性之间的平衡。


# 求解器架构介绍


## 车辆路径问题求解器

### 约束条件和目标函数

问题通过给定的约束条件和目标函数描述。约束条件和目标函数在求解器内部是等价得。一个问题由多组约束条件和目标函数构成，其中问题的成本等于所有的目标函数之和。

例如，经典的带时间窗车辆路径问题（Vehicle Routing Problem with Time Windows, VRPTW），是由容量约束、时间窗约束、最小化行驶距离以及最小化固定成本四组约束条件和目标函数构成。因此，在描述VRPTW的时候，需要从求解器提供的约束条件和目标函数集合中选取以下4个对象：

 1. CapacityConstraint
 2. TimeWindowConstraint
 3. MinimizeDistance
 4. MinimizeFixedCost

定义一个约束条件和目标函数时必须指定其需要的数据。例如，定义容量约束时必须指定每个节点的需求量（demand）以及每种车型的容量（Capacity）。同时，某些约束允许进行松弛，松弛后的惩罚成本将算入问题的总成本中。

### 构造初始解算子

构造初始解算子被用于构造初始解的贪心算法，根据问题的类型不同采用不同构造初始解算子。

### 构造初始解算法

求解器采用一个贪心算法快速构造可行的初始解，该算法在使用前需要指定一个构造初始解算子以及可用的车辆类型信息。

### 邻域搜索算子

邻域搜索算子被用于禁忌搜索算法，根据问题的类型和计算时间的要求不同采用不同的邻域搜索算子。



## 装箱问题求解器

![](/image/packing.png)

### 约束条件

关于物品在托盘上和箱子内摆放必须满足的规则，例如物品的底面受到支撑的比例不能小于某个给定阈值。装箱问题也是通过约束条件描述的，定义一个约束条件时同样必须指定其需要的数据。

### Block排序规则

算法在一开始会调用算法对物品做Block Building，这样可以加快搜索的速度。而算法选用的Block排序规则会影响算法的搜索路径，进而影响最终得到的解决方案。

# 求解器调用

求解器的交互通过json进行，用户通过向服务器发送问题的json文件，服务器运行求解器并将结果通过json返回给用户。对于一个json项目，假如键后面带\*，表示该项目可以省略，取默认值。

## 车辆路径问题

调用车辆路径问题求解器的json格式如下：
```json
{
	"Data":{},
	"Parameter":{},
	"Constraint":[],
	"ConstructionOperator":[],
	"Greedy":{},
	"LocalSearchOperator": [],
	"InitialSolution": {},
	"Nodes": {},
	"Algorithm":[]
}
```
* [Data](doc/routing/common/Data.md): 数据容器。
* [Parameter](doc/routing/common/Parameter.md): 算法参数。
* [Constraint](doc/routing/constraints/Constraint.md): 问题约束条件和目标函数列表。
* [ConstructionOperator](doc/routing/operators/ConstructionOperator.md): 构造初始解算子。
* [Greedy](doc/routing/common/Greedy.md): 提供可用的车辆信息。
* [LocalSearchOperator](doc/routing/operators/LocalSearchOperator.md): 邻域搜索算子。
* [InitialSolution](doc/routing/common/InitialSolution.md): 指定的初始解，既可以是一个完整的合法解，也可以是一个部分合法解。
* [Nodes](doc/routing/common/Nodes.md): 指定的初始解中尚未服务的顾客节点，假如InitialSolution未指定，则Nodes包含所有需要被服务的顾客节点。
* [Algorithm](doc/routing/common/Algorithm.md)\*：指定求解器运行的算法，如果缺省，则默认采用禁忌搜索算法。



## 装箱问题

调用装箱问题求解器的json的总体格式如下：

```json
{
	"Parameter": {},
	"Box": {},
	"Bin": {},
	"Tray": {},
	"Sequence": [],
	"Constraint": {},
	"BlockSortingRule": {}
}
```
* [Parameter](doc/packing/common/Parameter.md)：算法参数。
* [Box](doc/packing/common/Box.md)：物品信息。
* [Bin](doc/packing/common/Bin.md)：箱子信息。
* [Tray](doc/packing/common/Tray.md)：托盘信息。
* Sequence：Integer列表，车辆访问提货点的序列，如果只有一个提货点，则可以省略。
* [Constraint](doc/packing/constraints/Constraint.md)：约束条件。
* [BlockSortingRule](doc/packing/common/BlockSortingRule.md)：Block排序规则。



# 应用举例


## 车辆路径问题

以下提供几个经典问题的对应的json文件：

1. [带时间窗的车辆路径问题（Vehicle Routing Problem with Time Windows, VRPTW）](json/c201_input.json)。
2. [多仓库车辆路径问题（Multi-Depot Vehicle Routing Problem， MDVRP）](json/p22_input.json)。
3. [多车型车辆路径问题（Heterogeneous Vehicle Routing Problem, HVRP）](json/c100_20mix_input.json)。

除了直接求解问题外，求解器还支持检查解的合法性。检查解的合法性在json文件里只需要指定Constraint和InitialSolution这两项，并且只需要给出解中所要使用到的数据。例如，在距离和时间矩阵，只需要给出解中出现的边即可。[这里](json/c201_result_check.json)是一个检查VRPTW解合法性的例子。

## 装箱问题

以下提供几个经典问题得对应的json文件：

1. [不带任何约束的装箱问题](json/BR8_1_no_constraint.json)。
2. [带下表面支撑约束的装箱问题](json/BR8_1_support_area.json)。
3. [带多组约束的装箱问题](json/chongqing.json)。

# 返回结果

求解器以json的方式返回算法的运算结果，具体的json格式如下：

## 车辆路径问题


结果以[json文件](doc/routing/common/Result.md)方式返回，以下是几个例子：

1. [VRPTW](json/c201_result.json)。
2. [MDVRP](json/p22_result.json)。
3. [HVRP](json/c100_20mix_result.json)。

## 装箱问题

结果以[json文件](doc/packing/common/Result.md)方式返回，以下是几个例子：

1. [不带任何约束的装箱问题](json/BRBR8_1_no_constraint_result.json)。
2. [带下表面支撑约束的装箱问题](json/BR8_1_support_area_result.json)。
3. [带多组约束的装箱问题](json/chongqing_result.json)。
