# Parameter

## 描述

算法采用的参数。

## 调用JSON格式

```json
{
    "MultiThread": false,
    "MultiTrip": false,
    "TabuSearch_MaxIteration": 1000,
    "TabuSearch_TimeLimit": 100,
    "TabuSearch_MaxTabuTenure": 100,
    "TabuSearch_TenureDecayRate": 0.9,
    "TabuSearch_MinTabuTenure": 10,
    "TabuSearch_MinShakeTenure": 100,
    "TabuSearch_MinShakeIteration ": 20,
    "TabuSearch_Keep": false
  }
```
* MultiThread\*：Boolean，程序是否多线程运行，默认取false。
* MultiTrip\*：Boolean，车辆是否允许执行多趟，默认取false。
* TabuSearch_MaxIteration\*：Integer，禁忌搜索最大迭代次数，默认取100000。
* TabuSearch_TimeLimit\*：Integer，禁忌搜索运行时限，单位是秒，默认取3600。
* TabuSearch_MaxTabuTenure\*：Integer，禁忌搜索最大禁忌周长，默认取100。
* TabuSearch_TenureDecayRate\*：Double，禁忌搜索禁忌周长衰减速度，取值范围(0.0, 1.0)，默认取0.9。
* TabuSearch_MinTabuTenure\*：Integer，禁忌搜索最小禁忌周长，默认取0。
* TabuSearch_MinShakeTenure\*：Integer，禁忌搜索扰动周期，默认取20。
* TabuSearch_MinShakeIteration\*：Integer，禁忌搜索扰动次数，默认取100。
* TabuSearch_Keep：Boolean\*，禁忌搜索是否保存空车辆，默认取false。
