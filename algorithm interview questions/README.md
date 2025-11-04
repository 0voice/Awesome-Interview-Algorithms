# 大厂高频面试/笔试真题（LeetCode原题改编）

大厂命题常以 LeetCode 原题为基础，通过 **包装业务场景、调整输入输出约束、增加边界条件** 等方式改编，核心算法逻辑与原题高度一致。  
刷题时可先攻克对应 LeetCode 原题掌握核心思路，再结合本README的大厂改编场景强化练习，快速适配笔试面试的实际考察形式，提升解题效率与应试能力。

## 🧭 大厂刷题指南
[字节跳动](#字节跳动)

## 字节跳动
### 出题偏好
- **整体偏好**：
字节跳动算法面试整体偏好高频LeetCode Medium-Hard题 + 变体优化，强调时间/空间复杂度分析（如O(1)空间、O(log N)二分）和业务应用（e.g., 推荐系统的滑动窗口、视频处理的链表操作）。笔试/一面多2-3题（1小时AC），技术面（二/三面）追问边界（如k=1、空输入）和手撕代码。  
  - **高频主题占比**：动态规划（DP）35%、字符串/数组30%、链表/树20%、其他（堆/贪心/图）15%。  
  - **趋势**：AI融合增加（如序列DP变体），但基础不变。  
- **岗位偏好：**
  - 后端/客户端（e.g., 抖音、飞书）：链表/DP（40%），变体多（如k组翻转），业务场景如视频缓存。
  - 推荐/广告算法：图/贪心/堆（30%），加ML融合。
  - 前端/测试：算法少（<20%），偏项目；若考，多字符串/数组。
 
| 改编描述 | LeetCode原题 |
|----------|--------------|
| 使用最小堆（优先队列）合并k个有序链表，每次弹出最小节点并链接，O(n log k)时间优化，变体如分治两两合并或外部日志流处理。 | [LC23 合并 K 个升序链表](https://leetcode.cn/problems/merge-k-sorted-lists/) |
| DFS或BFS遍历2D网格标记'1'连通组件，统计岛屿数量，变体为计算最大岛屿面积（695），适用于图像分割或用户聚类场景，网格规模达10^6需优化空间。 | [LC200 岛屿数量](https://leetcode.cn/problems/number-of-islands/) |
| 二分搜索旋转有序数组，处理偏移点判断单调区间，变体带重复元素（81）以模拟噪声数据搜索，O(log n)时间关键。 | [LC33 搜索旋转排序数组](https://leetcode.cn/problems/search-in-rotated-sorted-array/) |
| 树DP递归计算左右子树最大贡献路径，求全局最大路径和，变体要求路径必须通过根节点，用于内容推荐树形权重优化。 | [LC124 二叉树中的最大路径和](https://leetcode.cn/problems/binary-tree-maximum-path-sum/) |
| 双向链表+哈希表实现LRU缓存，get/put O(1)操作，变体添加多线程锁或LFU淘汰策略，结合系统设计考察缓存一致性。 | [LC146 LRU 缓存机制](https://leetcode.cn/problems/lru-cache/) |
| BFS模拟球在迷宫中4方向滚动至目标停稳位置，变体添加动态墙壁生成，用于视频帧路径搜索或游戏导航。 | [LC490 迷宫中是否有路径](https://leetcode.cn/problems/the-maze/) |
| 栈模拟表达式计算，支持+ - * /忽略空格和优先级，变体扩展带括号（224），笔试中给示例如“2*3+5/1”考察边界处理。 | [LC227 基本计算器 II](https://leetcode.cn/problems/basic-calculator-ii/) |
| 双端队列维护窗口内递减序列，高效弹出最大值，变体求窗口中位数（480）用于实时数据流监控，如用户行为峰值分析。 | [LC239 滑动窗口最大值](https://leetcode.cn/problems/sliding-window-maximum/) |
| 按攻击降序排序后计算防御弱点，O(n)计数被支配角色，用于游戏推荐系统弱点排序变体。 | [LC1996 游戏中弱角色的数量](https://leetcode.cn/problems/the-number-of-weak-characters-in-the-game/) |
| 遍历价格数组累加所有上涨区间利润，变体添加手续费或单次交易（121），模拟推荐算法多次优化场景。 | [LC122 买卖股票的最佳时机 II](https://leetcode.cn/problems/best-time-to-buy-and-sell-stock-ii/) |
| 拓扑排序使用入度或DFS检测环，返回学习顺序，变体为任务依赖调度问题。 | [LC210 课程表 II](https://leetcode.cn/problems/course-schedule-ii/) |
| 栈记录索引计算有效括号子串长度，变体扩展为括号匹配计数，使用DP或栈两种思路。 | [LC32 最长有效括号](https://leetcode.cn/problems/longest-valid-parentheses/) |
| 回溯DFS枚举候选数组合和为目标，支持复用，变体无复用（40）添加背包容量约束。 | [LC39 组合总和](https://leetcode.cn/problems/combination-sum/) |
| 回溯法放置N皇后避免攻击，变体扩展为骑士巡游棋盘问题，考察剪枝优化。 | [LC51 N 皇后](https://leetcode.cn/problems/n-queens/) |
| Kadane算法O(n)扫描最大连续子数组和，变体固定k长度子数组求最大和。 | [LC53 最大子数组和](https://leetcode.cn/problems/maximum-subarray/) |
| 遍历找出最低买高卖单次最大利润，变体添加冷却期或手续费。 | [LC121 买卖股票的最佳时机](https://leetcode.cn/problems/best-time-to-buy-and-sell-stock/) |
| 归并排序链表自底向上合并，变体实现快速排序链表，O(n log n)时间。 | [LC148 排序链表](https://leetcode.cn/problems/sort-list/) |
| 回溯枚举拓扑和基础甜点组合求最近成本，变体背包问题中体积可负。 | [LC1671 最近的甜点成本](https://leetcode.cn/problems/closest-dessert-cost/) |
| 排序后双指针固定一数求两数和为0，变体扩展4Sum多指针。 | [LC15 三数之和](https://leetcode.cn/problems/3sum/) |
| 栈处理括号嵌套表达式计算，变体添加优先级运算符。 | [LC224 基本计算器](https://leetcode.cn/problems/basic-calculator/) |
| DFS洪水填充计算最大连通'1'面积，变体动态边界更新。 | [LC695 岛屿的最大面积](https://leetcode.cn/problems/max-area-of-island/) |
| 模拟方向遍历矩阵边界，变体逆向生成螺旋矩阵（59）。 | [LC54 螺旋矩阵](https://leetcode.cn/problems/spiral-matrix/) |
| DP转移方程dp[i][j] = min(上/左/对角) + 1求最大边长，变体优化空间为O(n)。 | [LC221 最大正方形](https://leetcode.cn/problems/maximal-square/) |
| 双堆（大根/小根）平衡维护中位数，变体动态窗口大小调整。 | [LC480 滑动窗口中位数](https://leetcode.cn/problems/sliding-window-median/) |
| BFS图搜索单词变换最短路径，变体双向BFS加速。 | [LC127 单词接龙](https://leetcode.cn/problems/word-ladder/) |
| 前序遍历字符串序列化，#分隔空节点反序列化，变体BFS层序编码压缩。 | [LC297 二叉树的序列化与反序列化](https://leetcode.cn/problems/serialize-and-deserialize-binary-tree/) |
| DFS或BFS+哈希标记克隆节点避免重复，变体处理环形图深拷贝。 | [LC133 克隆图](https://leetcode.cn/problems/clone-graph/) |
| 双指针从两端计算水位min(height) * 宽度，变体动态高度柱子。 | [LC42 接雨水](https://leetcode.cn/problems/trapping-rain-water/) |
| 小顶堆维护k大元素或快速选择分区O(n)平均，变体实时流第k大。 | [LC215 数组中的第K个最大元素](https://leetcode.cn/problems/kth-largest-element-in-an-array/) |
| 哈希+优先队列实现推特feed排序，按时间倒序，变体新闻流多用户排序。 | [LC355 设计推特](https://leetcode.cn/problems/design-twitter/) |
