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
- 走到一个尽量远的地方。
- 在 $1/-1$ 之间反复横跳。
前两者可在一次 BFS 时完成，剩下用一次 DFS，记录下到 $1/1$ 的沿途最短距离，需要加的 $1/1$ 的量，以及当前的权值需求，即可转移。
于是做到 $O(n+m)$。
## CFR 1036
### 4. E [Make it Zero](https://codeforces.com/contest/2124/problem/E)
Claim：最多两步即可。
于是尝试枚举两步的断点 $i,j$，那么我们可以解出六段数的和，通过这个可以直接构造出答案。
然后发现 $O(n^2)$ 过不去，于是尝试钦定 $j=i+1$ 然后过了，$O(n)$。
### 5. F [Appending Permutations](https://codeforces.com/contest/2124/problem/F1)
复读官方题解。
记 $f_{i,j}$ 表示填完 $i$ 的后缀，满足 $i$ 位为 $j$ 的方案数。
预处理 $c_{i,j}$ 使得其为最大的，使得 $j$ 向后合法延伸以 $c_{i,j}$ 为开头的等差数列的长度。
处理一个后缀和 $suf_{i,j}$ 表示在 $i$ 的后缀中可以插入 $j$ 的方案数，忽视 $a_i$ 之后上升段的合法性。
处理法是：$suf_{i,j}=\sum_{x=i}^n [c_{x,1}\ge j-1]\sum_{k}f_{x+j-1,k}$，理由是在 $x$ 放置 $1,2,\ldots,j-1$，然后前面填上 $j,j+1,\ldots$，后缀累积即可。
倒序枚举，每次枚举时：
- $f_{i,1}$，枚举后续长度，去除 $f_{i+l,l+1}$ 防止算重。
- $f_{i,>1}$，答案为 $suf_{i+1,j}-suf_{i+1+c_{i,j},j}$，差分去除掉违反限制的方案。