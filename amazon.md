# Coding:

1. 二分查找树，找和给定值最近的节点。扩展，找最近的K个点

2. 系统设计：会议安排系统。发会议邀请，检查冲突，取消会议等。如何扩展

3. 最长子串没有重复字符

4. 设计： 饭店餐位预定系统。

| 第一轮目测bar raiser， 全程纯behavior question，各种关于deadline, 关于和其他team member有冲突怎么办的问题第二轮先是bq问题，然后问了个给两个树的节点，每个节点有父指针，找lowest common ancester ，提出两种办法，一种是用set记录一个节点所有祖先包括自己的节点，然后把另一个节点从下往上通过父指针遍历，如果在set里出现了，则找到。另一种方法是找到到两个节点的路径，把长的路径先往上走K步 \(K 是路径长的差\)， 然后两个节点同时往上走，相遇点即LCA. 第三轮bq+ 写一个rate limiter class，如果一分钟某个ip请求超过十次拒绝请求 第四轮ood设计一个国际象棋，要实现棋子的move函数 第五轮设计一个message queue，实现三个函数，push pull和delete，要能处理每秒250k次的message push |
| :--- |


被烙印群殴了，店面

1

有一长串的矩阵相乘，找出time complexity最优的乘法。最先乘的用括号括起来。

比如A, B, C的dimension分别是2X1, 1X9, 9X1,返回A\(BC\)，因为先算BXC在被A乘是最优的。DFS+ memorization

2number of islands 1和2，合在其一起，写一个class

Onsite

每轮都有十几二十分钟的BQ+ experience

下面是题。

1. 给一堆商品以及每个商品的库存数，买家可以用一个价格bid 一个商品，在任意时间点卖家可以查询赢得某个商品的所有买家。Designclass 并实现这两个功能:Bid\(product, price\) 和 getListofWinners\(product\)。后来又问如果有很多商品，并且有很多买家。怎么处理并发以及平衡consistency和highavailability

2. Hiring manager。BQ比其他人多一些。给一个整数数组，找出uniquely第二大的数。如果是找第K个呢。

3. 视频远程面。全是BQ。

4. LC173 BST iterator + LC76 minimum windowsubstring

5. 上来就问：前面面的怎么样？

我说：挺好的。（其实真的觉得面的还不错，写完code面试官都说 looks good to me。）

他反问：everyone of them?

我说:yes。

然后开始BQ+ experience，过了快半个小时，他说来点technical的。设计kindle的文章朗读功能及实现。前端以及后端code的interface/class/function/data各是是什么样的，前端后端的code怎么call的，后端的server的详细构架是什么样的。怎么处理不同的语气，比如感叹句，问句，普通句子等，以及一些奇怪的人名怎么读，数字呢等等（这个函数其实就是LC273Integer to English words）。Coding 部分我还特意确认，这些数据结构及算法要implement出来吗，他说是的。我心里顿时就一万头草泥马呼啸而过。我说 时间很紧啊。他说 这是最后一轮了，没关系，takeyour time。写的我胳膊都抬不起来了。由于非常有时间紧迫感，很多部分都没写全，就是一略带过。有些函数的参数列表改来改去的，也有不一致的。中间他提了一些意见，我也只是口头同意，没有去改code，因为实在是好烦。然后他又追问了一下我的后端框架设计。结束时发现这轮竟然花了一个半小时。真是奇葩，这一轮就是BQ+ 系统设计 +OOD + 算法 + 数据结构的满汉全席。

第二天中午，预料之中的据信就来了。

# Design:

# 

# BQ:

https://www.linkedin.com/pulse/how-interview-amazon-leadership-david-anderson/



