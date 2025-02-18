# 堆简介

堆是一棵树，其每个节点都有一个键值，且每个节点的键值都大于等于/小于等于其父亲的键值。

每个节点的键值都大于等于其父亲键值的堆叫做小根堆，否则叫做大根堆。STL 中的 `priority_queue` 其实就是一个大根堆。

（小根）堆主要支持的操作有：插入一个数、查询最小值、删除最小值、合并两个堆、减小一个元素的值。

一些功能强大的堆（可并堆）还能（高效地）支持 merge 等操作。

一些功能更强大的堆还支持可持久化，也就是对任意历史版本进行查询或者操作，产生新的版本。

## 堆的分类

|         操作\\数据结构        |                                    配对堆                                    |       二叉堆      |       左偏树      |      二项堆      | 斐波那契堆         |
| :---------------------: | :-----------------------------------------------------------------------: | :------------: | :------------: | :-----------: | ------------- |
|        插入（insert）       |                                   $O(1)$                                  |   $O(\log n)$  |   $O(\log n)$  |     $O(1)$    |  $O(1)$       |
|     查询最小值（find-min）     |                                   $O(1)$                                  |     $O(1)$     |     $O(1)$     |  $O(\log n)$  |  $O(1)$       |
|    删除最小值（delete-min）    |                                $O(\log n)$                                |   $O(\log n)$  |   $O(\log n)$  |  $O(\log n)$  |  $O(\log n)$  |
|        合并 (merge)       |                                   $O(1)$                                  |     $O(n)$     |   $O(\log n)$  |  $O(\log n)$  |  $O(1)$       |
| 减小一个元素的值 (decrease-key) |  $o(\log n) (下界\Omega(\log \log n) ，\\\\上界 O(2^{2\sqrt{\log \log n}}) )$  |   $O(\log n)$  |    $O(logn)$   |  $O(\log n)$  |  $O(1)$       |
|         是否支持可持久化        |                                  $\times$                                 |  $\checkmark$  |  $\checkmark$  |               |  $\times$     |

习惯上，不加限定提到“堆”时往往都指二叉堆。
