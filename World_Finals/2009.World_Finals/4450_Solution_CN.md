# 2009 World Final: Deer-Proof Fence

##  Summary
平面上有n（n &lt;= 8）棵树苗，有一些鹿会吃这些树苗。现在要用围栏把这些树苗围起来，使鹿与树苗保持margin的距离。问如何围这些栅栏，使栅栏的长度最小。可以把多棵树用同一个栅栏围起来。

## Solution
由于选取哪些点用一个栅栏没有规律，因此使用类似搜索的动态规划。因为数据规模很小，所以使用状态压缩思想，用dp[x]表示选取点集状态为x所求的最小的耗费。明显dp[x] = min_{i∈{x}} {dp[i] + calc(x-i)}，其中i为x的一个二进制表示的一个子集，calc(st)能够计算出选择点集st放到同一个围栏的最小耗费，也就是点集的凸包的周长加上一个以margin为半径的圆的圆周。

预先使用calc函数算出所有点集的耗费后再进行DP即可。
