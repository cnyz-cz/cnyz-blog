
|  题目名称  | On Still Waters | Namida Ame |   Milk   | November |
| :----: | :-------------: | :--------: | :------: | :------: |
|  题目类型  |       传统        |     传统     |    传统    |    传统    |
|   目录   |      water      |    ame     |   milk   |   nov    |
| 可执行文件名 |      water      |    ame     |   milk   |   nov    |
| 输入文件名  |    water.in     |   ame.in   | milk.in  |  nov.in  |
| 输出文件名  |    water.out    |  ame.out   | milk.out | nov.out  |
|  时间限制  |                 |            |          |          |
|  空间限制  |                 |            |          |          |
| 子任务数目  |                 |            |          |          |
注意事项：
- 题目很简单，比某些神秘学校模拟赛简单。
- 题目全是原题，如果你做过原题，请不要声张，闷声发大财。
- 题目大样例不一定强，题目不一定有大样例。
<div style="page-break-after:always"></div>

# On Still Waters
## 题目描述
>Where is paradise? On the way home.
>What if night is dark? We'll be the shooting star.
>What if paths unsure? Courage must endure.
>We are about to reach the shore where hope can soar.
>—— [**On Still Waters**](https://www.bilibili.com/video/BV1d5kAYEEZr/?spm_id_from=333.337.search-card.all.click)

构造一个 $n\times n$ 的 $01$ 矩阵 $a$，满足：
- 每行恰有 $T$ 个 $1$；
- 对任意两行 $i,j$，有且只有一个 $k$，满足 $a_{i,k}=a_{j,k}=1$。
- 每行都是独一无二的。

可能无解，有无解的输出请参照输出格式。

## 输入格式
仅一行两个正整数 $n,T$。

## 输出格式
若无解，输出 `No`。
若有解，输出 `Yes`，而后，输出 $n$ 行 $n$ 个整数 $a_{i,j}$，表示你构造的矩阵 $a$。

## 样例
### 样例 1
```
3 2
```
```
Yes
1 1 0
1 0 1
0 1 1
```
### 样例 2
```
3 1
```
```
No
```
## 数据范围
对于全部子任务，均满足 $T\le n\le 500$。

| 子任务编号 |   特殊限制    |  分数  |
| :---: | :-------: | :--: |
|   1   | $n\le 4$  | $20$ |
|   2   | $T\le 3$  | $20$ |
|   3   | $n\le 10$ | $20$ |
|   4   |     无     | $40$ |
# Namida Ame
>