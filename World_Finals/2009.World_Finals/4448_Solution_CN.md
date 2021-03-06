# 2009 World Final: Conduit Packing

## Summary

给出平面上四个圆的直径，任意不重叠地放置这些圆，要求找出一个最小的圆包围这四个圆。求包围圆的半径。 

## Solution
二分答案，把问题转化为判定性问题：给出一个圆，其半径为R，判断这个圆是否能够容纳给出的四个圆。

判定时，枚举这些圆的布置排列。首先，假设把包围圆的圆心放置在原点，直径最大的圆肯定与包围圆相切，那么先放置直径最大的圆，使其与包围 圆内接（为了方便计算，第一个内圆放在(0,-R+r)的位置）。然后搜索剩下的三个圆的放置：求当前圆的放置方案时，可以肯定有两种最优的方案：

    * 与包围圆内切，及和一个已放置的内圆外切
    * 与两个已经放置的内圆外切 

求出符合条件的放置点，把当前圆放在这个点，然后再进行搜索。

把圆放置好后，判定这些圆是否相交。如果相交，那么就是这种搜索方案不成立。对于一个半径R，只要有一种搜索方案成立，那么这个R就是可行的。

PS：求与已知的两个圆的相切的圆，实际上可以转化成两个圆的相交问题。而且每次求出来必定有两个符合条件的圆。 
