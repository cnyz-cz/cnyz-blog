## CFR 1035
### 1. D [Token Removing](https://codeforces.com/contest/2119/problem/D)
对被删除的数的集合做讨论，假定其为 $B$，对于 $b\in B$：
- $\exists i\ge b$，$a_i\le b$。
那么可以对于 $B$ 中元素从大到小枚举，于是令 $f_{i,j}$ 表示当前枚举到第 $i$ 个下标，$B$ 中最大值是 $j$，容易讨论转移，$O(n^2)$。
### 2. E [And Constraint](https://codeforces.com/contest/2119/problem/E)
差一步。
对于所有的