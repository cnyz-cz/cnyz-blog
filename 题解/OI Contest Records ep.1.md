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
