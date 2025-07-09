### 1. [Kinoman](https://szkopul.edu.pl/problemset/problem/k-RYEjhwNTo_XdaCidXQUGMU/site/)
Source：22nd POI (2015) Stage 1
枚举 $r$ 考虑维护对应 $l$ 的答案。
只需要维护上一个种类相同的位置，支持区间加，区间 max 即可，容易使用线段树维护。
$O(n\log n)$。