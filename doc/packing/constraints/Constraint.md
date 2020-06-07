# Constraint

## 描述

约束条件分为两组，一组是关于物品装车的约束，另外一组是关于装托的约束。假如不存在需要装托的箱子，则关于装托的约束可以省略。目前求解器支持以下约束条件：

1. [SupportArea](SupportArea.md)：物品下表面支撑约束，即一个物品的下表面的支撑面占整个下表面积的比例不能小于给定的阈值。
2. [AreaSupportTrim](AreaSupportTrim.md)：同样是物品下表面支撑约束，但比SupportArea要弱。假如约束中包含支撑重量约束，那么应该采用AreaSupportTrim。
3. [CrossPlacement](CrossPlacement.md)：物品禁止错位堆码约束，即底面高于某个阈值的物品，必须由一个物品的上表面支撑，而不能够由多个物品组成的平面支撑。
4. [HeightLimit](HeightLimit.md)：物品摆放高度约束，即物品的摆放位置不能超过给定的高度。
5. PlacementLimit：不同提货点物品堆叠约束，即两个不同提货点的物品上下发生堆叠，上面的物品靠近车头的边距离下面物品靠近车门的边不能超过给定的阈值。
6. [Single](Single.md)：单独摆放约束，即物品上表面不等堆叠任何其他物品。
7. [StackLimit](StackLimit.md)：同种类型物品堆叠层数限制，即同一种类型的物品堆叠层数不能超过给定的阈值。
8. [TypeSupport](TypeSupport.md)：硬质的物品不能堆叠在软质的物品上。
9. [WeightSupportDifferentType](WeightSupportDifferentType.md)：不同种类型物品支撑重量约束，即直接或间接压在一个物品上表面的所有物品的重量不能超过给定阈值。物品A间接压到另外一个物品B是指存在至少一个物品C被物品A压到，并且C也间接压到B。
10. [WeightSupportAdvance](WeightSupportAdvance.md)：物品支撑重量约束和堆叠层数限制。假如两个物品的长宽之差的绝对值都小于某个阈值时，这两个物品被认为属于同种类型的物品。假如两个物品是同种类型，那么堆叠的层数不能超过给定的限制，并且上面的物品的重量不能超过下面物品的重量乘以一个给定的系数。假如物品不属于同种类型的物品，则直接或间接压在一个物品上表面的所有物品的重量不能超过给定阈值。
11. [LIFOWidth](LIFOWidth.md)：不同提货点物品摆放位置约束，即假如两个提货点排放的物品宽度小于某个阈值，那么这两个提货点的物品在车门方向的距离差距不能大于某个阈值。这个约束主要是考虑叉车装卸不同提货点物品时装卸的可行性。

## 调用JSON格式

```json
{
	"Truck": [],
	"Tray": []
}
```
* Truck：装车的约束列表。
* Tray：装托的约束列表。

