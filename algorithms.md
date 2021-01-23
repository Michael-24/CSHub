## 数据结构与算法

### leetcode hot100至少刷两遍，剑指offer至少刷两遍，重中之重！！

面试中90%的算法题都从leetcode hot100和剑指offer中出，刷两遍非常有必要。

### 红黑树的了解（平衡树，二叉搜索树），使用场景

红黑树是一种平衡二叉搜索树，它在每一个节点上都使用红色或黑色进行标记，通过一些性质确保它是始终平衡的。

* 每个节点要么红色要么黑色。
* 根节点是黑色。
* 如果节点为红，那么子节点必须为黑。
* 从任意节点到NULL的路径中包含的黑色节点的数量是相同的。（新插入的节点是红节点）

红黑树的插入，查询，删除在一般情况和最坏情况下的时间复杂度都是O(log(n))

应用场景主要是STL中map，set的实现，优点在于支持频繁的修改，因为查询删除插入时间复杂度都是logN。

### 判断一个链表是否有环，如何找到这个环的起点



### 实现一个strcpy函数（或者memcpy），如果内存可能重叠呢



### 实现一个循环队列



### 排序算法（写快排，归并排序，堆排序），算法的时间复杂度，空间复杂度，是否稳定等

| 算法名称 |                          时间复杂度                          | 稳定性 |
| :------: | :----------------------------------------------------------: | :----: |
| 选择排序 | <img src="http://latex.codecogs.com/svg.latex?O(n^2)" title="http://latex.codecogs.com/svg.latex?O(n^2)" /> | 不稳定 |
| 冒泡排序 | <img src="http://latex.codecogs.com/svg.latex?O(n^2)" title="http://latex.codecogs.com/svg.latex?O(n^2)" /> |  稳定  |
| 插入排序 | <img src="http://latex.codecogs.com/svg.latex?O(n^2)" title="http://latex.codecogs.com/svg.latex?O(n^2)" /> |  稳定  |
| 归并排序 | <img src="http://latex.codecogs.com/svg.latex?O(nlogn)" title="http://latex.codecogs.com/svg.latex?O(nlogn)" /> |  稳定  |
| 快速排序 | <img src="http://latex.codecogs.com/svg.latex?O(nlogn)" title="http://latex.codecogs.com/svg.latex?O(nlogn)" /> | 不稳定 |
|  堆排序  | <img src="http://latex.codecogs.com/svg.latex?O(nlogn)" title="http://latex.codecogs.com/svg.latex?O(nlogn)" /> | 不稳定 |

### 快速排序的实现

```

```



### 快排存在的问题，如何优化

优化方法：

* 在小数组上使用插入排序。
* 使用数组的一小部分的元素的中位数作为划分值。一种典型的做法是取样大小为3并使用居中的元素作为切分值。
* 把数组中和切分元素相同的元素聚集起来，下次切分的过程中不需要处理这些相同的元素。

### 堆排序的实现

```

```



### 归并排序的实现

```

```



### 反转一个链表

```

```



### Top K问题（可以采取的方法有哪些，各自优点？）



### Bitmap的使用，存储和插入方法



### 二叉树的先序、中序、后序遍历（非递归实现）



### 二叉树的公共祖先



### 1-n中有多少个1



### 数组的全排列



### N个骰子出现和为m的概率