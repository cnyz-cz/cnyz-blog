收录ge'da
### 1. [Kinoman](https://szkopul.edu.pl/problemset/problem/k-RYEjhwNTo_XdaCidXQUGMU/site/)
Source: POI 2015 Stage 1
枚举 $r$ 考虑维护对应 $l$ 的答案。
只需要维护上一个种类相同的位置，支持区间加，区间 max 即可，容易使用线段树维护。
$O(n\log n)$。
### 2. [Toilets](https://qoj.ac/contest/349/problem/407)
Source: JOISC 2016 Day 2
并非很难。
`F` 比 `M` 要自由很多，于是 set `F` 为 $1$，`M` 为 $-1$，那么后缀和就该 $\ge -1$。
据此处理出整体后缀和即可判断有无解，接下来考虑最小化。
由于不满度取的是 $\max$，其实基于贪心会发现我们一定会把后面的 `M` 提到第一个，这样一定最优。
然后就发现求答案等价于求最小后缀和，把后面的 `M` 挨个甩到前面去就行。
$O(\sum |S|)$。
### 3. [Territory](https://qoj.ac/contest/392/problem/3149)
Source: JOI 2016 Final
有参考代码。
可以首先模拟出第一轮每一个 $(x_i,y_i)$，接下来考虑怎么做。
模拟得到最终的向量 $(\Delta x,\Delta y)$，那么令 $x_i=x_i'+t\Delta x,y_i=y_i'+t\Delta y$，取 $x_i'\in[0,\Delta x)$，于是我们将 $(x_i,y_i)$ 转化到 $(x_i',y_i')$，每个点可以对应的 $t$ 恰是一段区间 $[t_m,t_m+k-1]$。
枚举左下端点 $(x_i,y_i)$，对 $(x_i+1,y_i),(x_i,y_i+1),(x_i+1,y_i+1)$ 对应的 $t$ 分别做区间求交即可得到答案。
时间复杂度 $O(n\log n)$。
细节：
1. $x_i=\Delta x-1$ 时，需要注意此时对应的 $(0,y_i-\Delta y)$，减掉的原因是对应求 $t$ 时的坐标转换，记得对应的 $t$ 区间也需要整体相减。
2. $t$ 可以为负数，set 交区间初始左端点要设成 $-n$ 而非 $0$。
3. 对于 $\Delta x<0$ 需要对第一轮的 $x_i$ 做取反，$\Delta x=0$，则交换 $x_i,y_i$，$\Delta x=\Delta y=0$，那么只需跑一轮，set $k=1$，$\Delta x$ 为任意非零数即可。