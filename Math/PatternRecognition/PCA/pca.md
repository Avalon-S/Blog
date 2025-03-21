# 主成分分析 Principal Component Analysis

## Portals

[直观地理解「协方差矩阵」](https://zhuanlan.zhihu.com/p/37609917)

## 理解&步骤

用于数据降维

![](Pics/L06P001.png)

省去某些维度信息

![](Pics/L06P002.png)

目标：将数据投影到新坐标系，使得信息保留最多

评判标准：使得数据分布尽量分散（方差大），作为主成分（坐标系）

保存信息：
1. 新坐标系原点
2. 新坐标系角度
3. 新坐标点

操作步骤：
1. 去中心化，将坐标原点放在数据中心
2. 找新的坐标系，找到投影后方差最大的方向（因为去中心化，所以所有数据点到原点的距离为常数。由勾股定理，当点到投影平面的距离最短时，投影点到原点的距离平方最大，也就是方差最大。因为到投影平面的距离短，所以保留了数据信息）

数据变换
1. 数据线性变换

    ![](Pics/L06P003.png)

2. 数据旋转变换

    ![](Pics/L06P004.png)

白数据$D$，x与y不相关，且都符合标准正态分布。通过先拉伸后旋转变化得到$D'$，此时x与y相关

![](Pics/L06P005.png)

![](Pics/L06P006.png)

现在我们已有的数据是$D'$，希望通过操作将已有数据还原成白数据

![](Pics/L06P007.png)

问题转化为求R？

**协方差矩阵的特征向量就是R**

![](Pics/L06P008.png)

对本例$\bar{x}、\bar{y}$均为0，因为已经进行区中心化

![](Pics/L06P009.png)

![](Pics/L06P010.png)

![](Pics/L06P011.png)

![](Pics/L06P01201.png)

这里体现出了，协方差矩阵的特征向量拼接起来就是R。L其实就是特征值组成的向量

![](Pics/L06P01202.png)

![](Pics/L06P013.png)

![](Pics/L06P014.png)

选取几个最大特征值对应的特征向量，将数据乘以这些特征向量所合成的矩阵即进行了映射（投影）。

![](Pics/L06P015.png)

![](Pics/L06P016.png)

outsider将会对求解结果造成很大影响

![](Pics/L06P017.png)