# BlockSortingRule


## 描述

Block排序规则同样分为装车时Block排序规则和装托时Block排序规则。假如不存在需要装托的物品，则装托时Block排序规则可以省略。

## 调用JSON格式

```json
{
  "Truck": "SectionFirst",
  "Tray": "VolumeFirst"
}
```
* Truck：String，装车时Block排序规则。
* Tray\*：String，装托时Block排序规则。

排序规则仅对于优先级一样的Block进行排序，目前求解器支持的排序规则有以下三个：

1. SectionFirst：Block的长X宽得到的面积越大排在越前面。
2. VolumeFirst：Block的体积越大越排在前面。
3. WidthFirst：Block的宽度越大越排在前面。
