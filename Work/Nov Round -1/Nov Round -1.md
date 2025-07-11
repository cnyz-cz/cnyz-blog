
|  题目名称  | On Still Waters | Namida Ame |   Milk   | November |
| :----: | :-------------: | :--------: | :------: | :------: |
|  题目类型  |       传统        |     传统     |    传统    |    传统    |
|   目录   |      water      |    ame     |   milk   |   nov    |
| 可执行文件名 |      water      |    ame     |   milk   |   nov    |
| 输入文件名  |    water.in     |   ame.in   | milk.in  |  nov.in  |
| 输出文件名  |    water.out    |  ame.out   | milk.out | nov.out  |
|  时间限制  |                 |            |          |          |
|  空间限制  |                 |            |          |          |
| 子任务数目  |        4        |     6      |          |          |
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
对于全部子任务，均满足 $1\le T\le n\le 500$。

| 子任务编号 |   特殊限制    |  分数  |
| :---: | :-------: | :--: |
|   1   | $n\le 4$  | $20$ |
|   2   | $T\le 3$  | $20$ |
|   3   | $n\le 10$ | $20$ |
|   4   |     无     | $40$ |
<div style="page-break-after:always"></div>
# Namida Ame
## 题目描述

>戸惑いと哀しみに狂う凪をなぞるように
>灯ひとつない夢の中をまた、ひとり、歩く？
>揺らいだ僕の心
>どうやって今、飛べると思う？
>—— [Namid[A]me](https://www.bilibili.com/video/BV1xM4y1k7S3/?spm_id_from=333.337.search-card.all.click)

>不休陀螺：在你的回合，当你没有手牌时，抽一张牌。

总之你正在游玩《Slay the Spire》并获得了不休陀螺，由于一些恶趣味，你的手牌上限被限制在了 $1$。
用 $(a_i,b_i)$ 表示一张牌，其中 $a_i$ 为打出这张牌所需的费用，$b_i$ 为打出这张牌后，可以获得的费用。
现在有 $n$ 张牌组成序列，初始有 $E$ 点费用，你对能不能赢游戏不感兴趣，而是对这一组牌可不可以达成稳定无限感兴趣，具体地：
- 我们称一次打牌为，随机从当前牌堆中抽取一张牌，若费用足够便直接打出，打出的牌进入弃牌堆；
- 经过若干次打牌，牌堆中不再有牌，此时将弃牌堆中的牌移至牌堆。
- 若无论随机打牌的顺序如何，总可以进行无数次打牌，则称这个卡组为稳定无限。

你不仅对当前卡组感兴趣，你还在想，如果取出任意一个区间作为卡组，这个区间稳定无限的情况有多少种？求出稳定无限的区间总数。

## 输入格式
第一行为两个正整数 $n,E$。
接下来一行 $n$ 个正整数 $a_i$。
接下来一行 $n$ 个正整数 $b_i$。

## 输出格式
仅一行一个整数，表示稳定无限的区间总数。

## 样例
### 样例 1
```
2 0
0 0
1 1
```
```
3
```

### 样例 2
```
5 10
9 10 10 0 2
8 5 6 2 5
```
```
4
```

### 样例 3
```
5 10
8 1 6 4 10
7 6 1 8 5
```
```
5
```

### 样例 4
```
10 43
7 9 8 4 2 1 2 13 12 4
4 13 9 6 9 12 13 5 13 10
```
```
51
```

### 样例 5
见附加文件 `ame5.in/ame5.out`，该组数据满足 Subtask 1 的特殊限制。

### 样例 6
见附加文件 `ame6.in/ame6.out`，该组数据满足 Subtask 4 的特殊限制。

### 样例 7
见附加文件 `ame7.in/ame7.out`，该组数据满足 Subtask 5 的特殊限制。

### 样例 8
见附加文件 `ame8.in/ame8.out`。

## 数据范围
对于全部子任务，有 $1\le n\le 10^6$，$0\le E,a_i,b_i\le 10^9$。