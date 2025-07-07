## CFR 1035
### 1. D [Token Removing](https://codeforces.com/contest/2119/problem/D)
对被删除的数的集合做讨论，假定其为 $B$，对于 $b\in B$：
- $\exists i\ge b$，$a_i\le b$。
那么可以对于 $B$ 中元素从大到小枚举，于是令 $f_{i,j}$ 表示当前枚举到第 $i$ 个下标，$B$ 中最大值是 $j$，容易讨论转移，$O(n^2)$。
### 2. E [And Constraint](https://codeforces.com/contest/2119/problem/E)
差一步。
对于所有的 $a_i$ 我们可以跑出一大把对 $b_i$ bit 的限制，然后留下一堆 bit 可取 $0/1$。
结论：最终一个数最多 set 一个 bit 到 $1$。
基于此，直接 dp $f_{i,j}$ 表示 $i$ set 的 bit 是第 $j$ 位，所对应的最小答案，于是在 $O(n\log^2V)$ 的时间复杂度解决问题。
### 3. F [Volcanic Eruptions](https://codeforces.com/contest/2119/problem/F)
可以这样 claim，我们最终的路径会形如：
- 一条 $1/-1$ 交叉链。
- 在 $1/1$ 之间反复，累计 $S$ 到一定量。
- 在
