# 大厂高频面试/笔试真题（LeetCode原题改编）

大厂命题常以 LeetCode 原题为基础，通过 **包装业务场景、调整输入输出约束、增加边界条件** 等方式改编，核心算法逻辑与原题高度一致。  
刷题时可先攻克对应 LeetCode 原题掌握核心思路，再结合本README的大厂改编场景强化练习，快速适配笔试面试的实际考察形式，提升解题效率与应试能力。

## 🧭 快速导航
[字节跳动](#字节跳动)  
[阿里巴巴](#阿里巴巴)  
[腾讯](#腾讯)
## 字节跳动
### 出题偏好
- **整体偏好**：
字节跳动算法面试/笔试以「高频算法题深度挖掘 + 工程编码能力强考察」为核心，极度重视基础算法的熟练度与编码实现效率。笔试时长通常 2 小时，题量以 3-4 道编程题为主（算法岗多为 4 题，后端/前端岗常为 3-4 题），包含 1-2 道 LeetCode Hard 难度题，对边界条件处理、代码鲁棒性（如空输入、极端数据）要求严苛；技术一面 40% 时间聚焦算法，需在规定时间内手撕代码并优化（如从暴力解到最优解的演进），二面、三面才逐步深入项目与系统设计。整体风格前期偏“纯粹算法能力考察”，近年结合短视频、直播等核心业务的场景化题目占比显著提升。
  - **高频主题占比**：动态规划（DP）（32%）、字符串/数组（30%）、链表/树（23%）、其他（堆/贪心/图/设计类）（15%）。  
  - **趋势**：算法考察深度持续增加（同一题目追问多解法、复杂度优化），业务场景融合加强（如“抖音视频流的滑动窗口推荐变体”“直播间弹幕系统如何设计”），系统设计环节对高并发、大数据处理（如适配 Flink/Spark 框架）的要求愈发明确。
- **岗位偏好：**
  - 后端（e.g., 抖音、今日头条、飞书）：动态规划/数组/链表（45%），高频题集中于“K个一组翻转链表”“买卖股票的最佳时机”“二叉树的最近公共祖先”，变体多为“多约束优化问题”（如带时间窗口的订单统计变体），业务场景如短视频流的实时推荐排序、用户行为日志的高效存储与查询。
  - 算法岗（推荐/广告/搜索）：动态规划/图论/贪心（48%），侧重“大规模数据下的算法适配”（如亿级短视频的召回算法优化），融合特征工程与模型推理效率问题（如基于用户行为的序列 DP 设计），常考察“推荐精准度与多样性的平衡”等业务相关算法设计。
  - 客户端（e.g., 抖音客户端、剪映）：链表/树/数组（42%），“反转链表”“二叉树的前序遍历”等题目考察频次极高，偏“内存优化与高效实现”（如 O(1) 空间复杂度的链表操作），业务场景如本地视频素材的快速剪辑处理、离线缓存数据的同步与更新。
  - 数据平台/大数据：分治/哈希/图论（38%），核心考察“海量数据处理能力”（如超大规模日志的实时分析变体），需适配 Spark/Flink 等计算框架，结合字节数据中台场景设计高吞吐、低延迟的算法方案。

 ### 改编题目
| 改编描述 | 业务场景 | LeetCode原题 |
|----------|----------|--------------|
| 给定K个有序链表，合并成一个有序链表。面试常问：分治两两合并或外部日志流处理优化。 | 字节视频时间戳同步或日志聚合场景 | [LC23 合并 K 个升序链表](https://leetcode.cn/problems/merge-k-sorted-lists/) |
| 给定0/1网格，统计连通岛屿数量。面试常问：计算最大岛屿面积（LC695）。 | 字节图像分割或用户兴趣聚类场景 | [LC200 岛屿数量](https://leetcode.cn/problems/number-of-islands/) |
| 给定旋转有序数组，搜索目标值。面试常问：带重复元素（LC81）噪声处理。 | 字节推荐ID列表二分查询 | [LC33 搜索旋转排序数组](https://leetcode.cn/problems/search-in-rotated-sorted-array/) |
| 给定二叉树，求最大路径和（任意节点）。面试常问：路径必须通过根节点。 | 字节内容推荐树形权重优化 | [LC124 二叉树中的最大路径和](https://leetcode.cn/problems/binary-tree-maximum-path-sum/) |
| 实现LRU缓存，支持get/put O(1)操作。面试常问：多线程锁或LFU淘汰（LC460）。 | 字节抖音视频元数据缓存设计 | [LC146 LRU 缓存机制](https://leetcode.cn/problems/lru-cache/) |
| 给定迷宫网格，从起点滚球到目标停稳位置。面试常问：动态墙壁生成。 | 字节视频帧路径搜索或游戏导航 | [LC490 迷宫中是否有路径](https://leetcode.cn/problems/the-maze/) |
| 给定表达式字符串，计算+ - * /值（忽略优先级）。面试常问：带括号扩展（LC224），示例“2*3+5/1”。 | 字节配置表达式解析 | [LC227 基本计算器 II](https://leetcode.cn/problems/basic-calculator-ii/) |
| 给定数组和窗口k，求每个窗口最大值。面试常问：窗口中位数（LC480）。 | 字节用户行为实时峰值监控 | [LC239 滑动窗口最大值](https://leetcode.cn/problems/sliding-window-maximum/) |
| 给定角色攻击/防御数组，计数弱角色（被支配）。面试常问：弱点排序扩展。 | 字节游戏推荐系统 | [LC1996 游戏中弱角色的数量](https://leetcode.cn/problems/the-number-of-weak-characters-in-the-game/) |
| 给定股票价格数组，允许多次买卖最大利润。面试常问：手续费或单次（LC121）。 | 字节推荐多次优化模拟 | [LC122 买卖股票的最佳时机 II](https://leetcode.cn/problems/best-time-to-buy-and-sell-stock-ii/) |
| 给定课程和先修关系，返回学习顺序（拓扑排序）。面试常问：任务依赖调度。 | 字节项目流程管理 | [LC210 课程表 II](https://leetcode.cn/problems/course-schedule-ii/) |
| 给定括号字符串，求最长有效子串长度。面试常问：括号匹配计数，使用DP或栈。 | 字节表达式验证 | [LC32 最长有效括号](https://leetcode.cn/problems/longest-valid-parentheses/) |
| 给定候选数组和目标，求所有组合（可复用）。面试常问：无复用（LC40）+背包约束。 | 字节资源组合生成 | [LC39 组合总和](https://leetcode.cn/problems/combination-sum/) |
| 在N*N棋盘放置N皇后，无攻击。面试常问：骑士巡游扩展，剪枝优化。 | 字节棋盘约束问题 | [LC51 N 皇后](https://leetcode.cn/problems/n-queens/) |
| 给定整数数组，求连续子数组最大和。面试常问：固定k长度子数组。 | 字节交易序列优化 | [LC53 最大子数组和](https://leetcode.cn/problems/maximum-subarray/) |
| 给定股票价格数组，求单次买卖最大利润。面试常问：冷却期或手续费。 | 字节交易模拟 | [LC121 买卖股票的最佳时机](https://leetcode.cn/problems/best-time-to-buy-and-sell-stock/) |
| 给定链表，实现O(n log n)排序。面试常问：快速排序变体。 | 字节数据链表排序 | [LC148 排序链表](https://leetcode.cn/problems/sort-list/) |
| 给定基础/高级甜点成本，求最近目标成本组合。面试常问：背包体积可负。 | 字节资源枚举优化 | [LC1671 最近的甜点成本](https://leetcode.cn/problems/closest-dessert-cost/) |
| 给定整数数组，找出和为0的三元组（无重复）。面试常问：4Sum多指针扩展。 | 字节多维特征匹配 | [LC15 三数之和](https://leetcode.cn/problems/3sum/) |
| 给定带括号表达式，计算值。面试常问：优先级运算符添加。 | 字节嵌套配置计算 | [LC224 基本计算器](https://leetcode.cn/problems/basic-calculator/) |
| 给定0/1网格，计算最大岛屿面积。面试常问：动态边界更新。 | 字节连通区域分析 | [LC695 岛屿的最大面积](https://leetcode.cn/problems/max-area-of-island/) |
| 给定矩阵，按螺旋顺序遍历元素。面试常问：逆向生成（LC59）。 | 字节矩阵数据提取 | [LC54 螺旋矩阵](https://leetcode.cn/problems/spiral-matrix/) |
| 给定0/1矩阵，求最大全1正方形边长。面试常问：O(n)空间优化。 | 字节矩阵模式识别 | [LC221 最大正方形](https://leetcode.cn/problems/maximal-square/) |
| 给定数组和窗口k，求每个窗口中位数。面试常问：动态窗口调整。 | 字节数据流中位分析 | [LC480 滑动窗口中位数](https://leetcode.cn/problems/sliding-window-median/) |
| 给定开始词、结束词和字典，求最短变换序列。面试常问：双向BFS加速。 | 字节单词梯度优化 | [LC127 单词接龙](https://leetcode.cn/problems/word-ladder/) |
| 序列化/反序列化二叉树（字符串表示）。面试常问：BFS层序压缩。 | 字节树数据持久化 | [LC297 二叉树的序列化与反序列化](https://leetcode.cn/problems/serialize-and-deserialize-binary-tree/) |
| 给定图节点，深拷贝整个图。面试常问：环形图处理。 | 字节图结构克隆 | [LC133 克隆图](https://leetcode.cn/problems/clone-graph/) |
| 给定高度数组，计算陷水总量。面试常问：动态高度柱子。 | 字节柱状资源模拟 | [LC42 接雨水](https://leetcode.cn/problems/trapping-rain-water/) |
| 给定数组，找出第K大元素。面试常问：实时流处理。 | 字节排名系统 | [LC215 数组中的第K个最大元素](https://leetcode.cn/problems/kth-largest-element-in-an-array/) |
| 设计Twitter系统，支持发帖/关注/feed。面试常问：新闻流多用户排序。 | 字节社交feed设计 | [LC355 设计推特](https://leetcode.cn/problems/design-twitter/) |


## 阿里巴巴
### 出题偏好
- **整体偏好**：
阿里巴巴算法面试/笔试核心围绕「LeetCode 高频题 + 业务场景深度改编」，注重算法的工程落地性（如大数据处理、高并发场景适配）和代码鲁棒性（异常处理、边界用例覆盖）。笔试通常 3-4 题（1.5 小时），包含 1 道 Hard 题；技术面（一/二面）以 Medium 题为主，追问「优化方向」（如海量数据下的空间优化）和「业务迁移」（如将算法适配电商场景）。
  - **高频主题占比**：数组/字符串（32%）、动态规划（DP）（28%）、哈希表/贪心（18%）、树/图（15%）、其他（堆/并查集/二分）（7%）。
  - **趋势**：强绑定业务场景（如电商交易、物流调度），新增「大数据算法」（如分治、外排序变体），基础算法仍是核心但需结合场景思考。
- **岗位偏好：**
  - 后端（e.g., 淘宝、天猫、阿里云）：数组/DP/哈希表（45%），变体多为「多约束条件」（如带权重的背包变体），业务场景如订单排序、库存调度、分布式缓存优化。
  - 算法岗（推荐/广告/搜索）：图/贪心/DP（40%），侧重「大规模数据适配」（如亿级用户的最短路径变体），融合 ML 特征工程（如基于用户行为的序列 DP）。
  - 客户端（e.g., 支付宝、钉钉）：字符串/链表/树（35%），偏「内存优化型变体」（如 O(1) 空间的链表操作），业务场景如本地数据同步、界面渲染优化。
  - 大数据/数仓：分治/外排序/哈希（30%），核心考察「海量数据处理」（如超大数据组的逆序对变体），适配 Hadoop/Spark 场景。
### 改编题目
| 改编描述 | 业务场景 | LeetCode原题 |
|----------|----------|--------------|
| 给定一个字符串，找出其中没有重复字符的最长子串长度。面试常问：如果限制最多K个不同字符，怎么改？ | 阿里文本搜索场景，如查询历史无重复关键词提取 | [LC3 最长无重复字符的子串](https://leetcode.cn/problems/longest-substring-without-repeating-characters/) |
| 给定两个有序数组，找出合并后的中位数。面试常问：数组长度奇偶不同时边界处理。 | 阿里风控，如合并用户行为分数求平均风险值 | [LC4 寻找两个正序数组的中位数](https://leetcode.cn/problems/median-of-two-sorted-arrays/) |
| 给定一个字符串，找出最长的回文子串。面试常问：奇偶长度中心扩展。 | 阿里商品标题模式匹配，如检测对称描述 | [LC5 最长回文子串](https://leetcode.cn/problems/longest-palindromic-substring/) |
| 给定高度数组，求两个柱子间最大水容积（宽度*最小高度）。面试常问：动态调整高度变化。 | 阿里资源分配，如负载均衡模拟 | [LC11 盛最多水的容器](https://leetcode.cn/problems/container-with-most-water/) |
| 给定整数数组，找出和为0的三元组（无重复）。面试常问：扩展到4Sum多维去重。 | 阿里订单特征匹配 | [LC15 三数之和](https://leetcode.cn/problems/3sum/) |
| 给定数字字符串，生成所有可能的字母组合（2-9映射）。面试常问：添加字典过滤有效词。 | 阿里序列生成，如验证码组合 | [LC17 电话号码的字母组合](https://leetcode.cn/problems/letter-combinations-of-a-phone-number/) |
| 给定括号字符串，判断是否有效匹配。面试常问：多类型括号嵌套。 | 阿里配置验证，如JSON表达式解析 | [LC20 有效的括号](https://leetcode.cn/problems/valid-parentheses/) |
| 给定两个有序链表，合并成一个有序链表。面试常问：扩展到K个链表（LC23）。 | 阿里日志和订单流融合 | [LC21 合并两个有序链表](https://leetcode.cn/problems/merge-two-sorted-lists/) |
| 给定整数数组，求连续子数组的最大和。面试常问：固定k长度子数组。 | 阿里交易额连续优化 | [LC53 最大子数组和](https://leetcode.cn/problems/maximum-subarray/) |
| 给定股票价格数组，求单次买卖最大利润。面试常问：添加冷却期或手续费。 | 阿里交易风控模拟 | [LC121 买卖股票的最佳时机](https://leetcode.cn/problems/best-time-to-buy-and-sell-stock/) |
| 给定字符串和单词字典，判断是否能拆分成字典词。面试常问：返回所有拆分方式（LC140）。 | 阿里商品描述分词 | [LC139 单词拆分](https://leetcode.cn/problems/word-break/) |
| 给定0/1网格，统计连通岛屿数量。面试常问：计算最大岛屿面积（LC695）。 | 阿里用户聚类或图片分割 | [LC200 岛屿数量](https://leetcode.cn/problems/number-of-islands/) |
| 给定单链表，反转整个链表。面试常问：k组分段翻转（LC25）。 | 阿里日志链表处理 | [LC206 反转链表](https://leetcode.cn/problems/reverse-linked-list/) |
| 给定课程和先修关系，判断是否能完成（无环）。面试常问：返回顺序（LC210）。 | 阿里项目依赖管理 | [LC207 课程表](https://leetcode.cn/problems/course-schedule/) |
| 给定数组，找出第K大元素。面试常问：实时流处理。 | 阿里热搜实时排名 | [LC215 数组中的第K个最大元素](https://leetcode.cn/problems/kth-largest-element-in-an-array/) |
| 给定二叉树和两个节点，找最近公共祖先。面试常问：多节点LCA预处理。 | 阿里组织架构查询 | [LC236 二叉树的最近公共祖先](https://leetcode.cn/problems/lowest-common-ancestor-of-a-binary-tree/) |
| 给定数组，计算每个元素除自身外的乘积（无除法）。面试常问：O(1)空间优化。 | 阿里用户行为权重统计 | [LC238 除自身以外数组的乘积](https://leetcode.cn/problems/product-of-array-except-self/) |
| 给定数组和窗口大小k，求每个窗口的最大值。面试常问：窗口中位数（LC480）。 | 阿里订单价格滑动分析 | [LC239 滑动窗口最大值](https://leetcode.cn/problems/sliding-window-maximum/) |
| 给定面额数组和总金额，求最少硬币数。面试常问：完全背包变体。 | 阿里资源分配模拟 | [LC322 零钱兑换](https://leetcode.cn/problems/coin-change/) |
| 给定正整数数组，判断是否能分割成两个等和子集。面试常问：0/1背包扩展。 | 阿里流量均衡分流 | [LC416 分割等和子集](https://leetcode.cn/problems/partition-equal-subset-sum/) |
| 给定二叉树，计算最长路径（直径）。面试常问：平衡树检查。 | 阿里决策树结构分析 | [LC543 二叉树的直径](https://leetcode.cn/problems/diameter-of-binary-tree/) |
| 给定两棵二叉树，按节点值合并（非空相加）。面试常问：处理空节点。 | 阿里用户画像数据融合 | [LC617 合并两棵二叉树](https://leetcode.cn/problems/merge-two-binary-trees/) |
| 给定字符串，计数所有回文子串数量。面试常问：奇偶中心扩展。 | 阿里评论情感文本分析 | [LC647 回文子串](https://leetcode.cn/problems/palindromic-substrings/) |
| 给定有序数组和目标值，实现二分查找。面试常问：旋转数组偏移（LC33）。 | 阿里商品ID有序查询 | [LC704 二分查找](https://leetcode.cn/problems/binary-search/) |
| 给定单链表，找中间节点。面试常问：奇偶长度处理。 | 阿里分页链表操作 | [LC876 链表的中间结点](https://leetcode.cn/problems/middle-of-the-linked-list/) |
| 给定天数数组和票价，求最低旅行成本。面试常问：日程约束优化。 | 阿里员工出差路径规划 | [LC983 最低票价](https://leetcode.cn/problems/minimum-cost-for-tickets/) |
| 给定成本数组，贪心分配两城市最小总成本。面试常问：多城市扩展。 | 阿里多地调度资源分配 | [LC1029 两城市之间最优路径](https://leetcode.cn/problems/two-city-scheduling/) |
| 给定两个字符串，求最长公共子序列长度。面试常问：编辑距离相似度。 | 阿里商品描述序列匹配 | [LC1143 最长公共子序列](https://leetcode.cn/problems/longest-common-subsequence/) |
| 实现LRU缓存，支持get/put O(1)操作。面试常问：LFU频率变体（LC460）。 | 阿里淘宝热搜缓存设计 | [LC146 LRU缓存机制](https://leetcode.cn/problems/lru-cache/) |
| 给定整数数组，求连续子数组的最大乘积。面试常问：负数边界处理。 | 阿里连续收益乘积优化 | [LC152 乘积最大子数组](https://leetcode.cn/problems/maximum-product-subarray/) |

## 腾讯
### 出题偏好
- **整体偏好**：
腾讯算法面试/笔试以「LeetCode 高频题为基础，强绑定业务场景创新改编」为核心，既注重基础算法的掌握深度，也强调技术与业务的结合能力（如社交场景的图算法、游戏场景的动态规划）。笔试通常 3-4 题（1.5 小时），包含 1-2 道 Medium 题和 1 道 Hard 题；技术面（一/二面）以 Medium 题为主，重点追问「算法优化细节」（如从 O(N²) 到 O(N log N) 的优化思路）和「边界场景处理」（如空输入、极端数据规模），三面可能加入「业务方案设计」（如如何用算法解决微信消息同步问题）。
  - **高频主题占比**：动态规划（DP）（30%）、图/树（25%）、数组/字符串（20%）、设计类（如缓存、队列）（15%）、其他（贪心/堆/二分）（10%）。
  - **趋势**：大模型相关算法融合增加（如基于序列 DP 的文本生成优化），社交、游戏、内容生态的业务场景题占比提升，但基础算法（如 DP、图遍历）仍是考察核心。
- **岗位偏好：**
  - 后端（e.g., 微信、QQ、腾讯云）：图/DP/设计类（42%），变体多为「多场景约束」（如带权限控制的图遍历变体），业务场景如微信朋友圈点赞计数、云服务器资源调度、消息队列延迟处理。
  - 算法岗（推荐/广告/游戏）：DP/图/机器学习融合（45%），侧重「大规模数据适配」（如亿级用户的推荐列表排序变体），融合特征工程（如基于用户游戏行为的动态规划状态设计）。
  - 客户端（e.g., 微信客户端、腾讯视频）：数组/字符串/链表（38%），偏「内存与性能优化」（如 O(1) 空间的链表去重），业务场景如本地视频缓存清理、聊天记录搜索匹配、界面滑动流畅性优化。
  - 游戏开发岗：动态规划/图/数学（40%），核心考察「场景化算法设计」（如游戏地图寻路的 A* 算法变体、角色技能伤害计算的数学模型），适配游戏实时交互场景。

### 改编题目
| 改编描述 | 业务场景 | LeetCode原题 |
|----------|----------|--------------|
| 给定数组，求子数组最大和。面试常问：k长子数组变体。 | 腾讯游戏分数连续计算 | [LC53 最大子数组和](https://leetcode.cn/problems/maximum-subarray/) |
| 给定链表，反转整个链表。面试常问：k组翻转。 | 腾讯日志链路处理 | [LC206 反转链表](https://leetcode.cn/problems/reverse-linked-list/) |
| 给定点数组，计算直线上最多点数（斜率哈希）。面试常问：重合点处理。 | 腾讯游戏坐标碰撞检测 | [LC149 直线上最多的点数](https://leetcode.cn/problems/max-points-on-a-line/) |
| 给定点数组和K，找原点最近K个点（欧氏距离）。面试常问：优先队列。 | 腾讯推荐KNN搜索 | [LC973 K 个最近的点](https://leetcode.cn/problems/k-closest-points-to-origin/) |
| 给定字符串，生成所有有效括号组合。面试常问：n=10边界。 | 腾讯配置生成 | [LC22 括号生成](https://leetcode.cn/problems/generate-parentheses/) |
| 给定数组和目标，求两数之和索引。面试常问：三数扩展。 | 腾讯支付双交易匹配 | [LC1 两数之和](https://leetcode.cn/problems/two-sum/) |
| 给定旋转数组，搜索目标。面试常问：重复元素（LC81）。 | 腾讯ID列表查询 | [LC33 搜索旋转排序数组](https://leetcode.cn/problems/search-in-rotated-sorted-array/) |
| 给定0/1网格，统计岛屿数量。面试常问：最大面积（LC695）。 | 腾讯地图聚类 | [LC200 岛屿数量](https://leetcode.cn/problems/number-of-islands/) |
| 给定数组，找出第K大元素。面试常问：实时流。 | 腾讯热搜排名 | [LC215 数组中的第K个最大元素](https://leetcode.cn/problems/kth-largest-element-in-an-array/) |
| 给定区间数组，合并重叠区间。面试常问：多区间排序。 | 腾讯会议时间合并 | [LC56 合并区间](https://leetcode.cn/problems/merge-intervals/) |
| 给定字符串，计算编辑距离。面试常问：DP空间优化。 | 腾讯文本相似匹配 | [LC72 编辑距离](https://leetcode.cn/problems/edit-distance/) |
| 给定数组，求除自身外乘积（无除法）。面试常问：O(1)空间。 | 腾讯权重统计 | [LC238 除自身以外数组的乘积](https://leetcode.cn/problems/product-of-array-except-self/) |
| 给定数组和k，求窗口最大值。面试常问：中位数（LC480）。 | 腾讯滑动订单分析 | [LC239 滑动窗口最大值](https://leetcode.cn/problems/sliding-window-maximum/) |
| 给定面额和金额，求最少硬币数。面试常问：完全背包。 | 腾讯支付分配 | [LC322 零钱兑换](https://leetcode.cn/problems/coin-change/) |
| 给定数组，判断等和子集。面试常问：0/1背包。 | 腾讯流量分流 | [LC416 分割等和子集](https://leetcode.cn/problems/partition-equal-subset-sum/) |
| 给定二叉树，计算直径。面试常问：平衡检查。 | 腾讯树分析 | [LC543 二叉树的直径](https://leetcode.cn/problems/diameter-of-binary-tree/) |
| 给定两棵树，节点值合并。面试常问：空节点处理。 | 腾讯数据融合 | [LC617 合并两棵二叉树](https://leetcode.cn/problems/merge-two-binary-trees/) |
| 给定字符串，计数回文子串。面试常问：奇偶扩展。 | 腾讯文本分析 | [LC647 回文子串](https://leetcode.cn/problems/palindromic-substrings/) |
| 给定有序数组，实施二分查找。面试常问：旋转偏移（LC33）。 | 腾讯商品查询 | [LC704 二分查找](https://leetcode.cn/problems/binary-search/) |
| 给定链表，找中间节点。面试常问：奇偶处理。 | 腾讯分页操作 | [LC876 链表的中间结点](https://leetcode.cn/problems/middle-of-the-linked-list/) |

## 美团

### 出题偏好
- **整体偏好**：
美团算法面试/笔试以「LeetCode 高频题落地适配 + 本地生活业务深度绑定」为核心，既强调基础算法的工程化实现能力，更注重算法与外卖、到店、即时零售等核心业务的结合度（如配送路径优化、商家推荐排序）。笔试时长通常 2 小时，题量因岗位差异显著：算法岗为「选择题 + 5 道编程题」，后端岗为「选择题 + 3 道编程题」，客户端/数据岗为「选择题 + 2-3 道编程题」，整体难度呈梯度分布（如前 1-2 题偏基础，最后 1 题达 Medium-Hard 难度）；技术一面聚焦「算法实现与复杂度分析」，要求手撕代码并说明时空开销（如 O(n) 时间 + O(1) 空间解决链表问题），二面侧重「业务场景拆解」，三面会加入「系统方案与商业指标关联」（如算法优化如何降低外卖配送超时率）。
  - **高频主题占比**：贪心（25%）、动态规划（DP）（20%）、图/树（20%）、数组/字符串（20%）、其他（二分/堆/搜索）（15%）。  
  - **趋势**：大模型技术融合题占比上升（如基于贪心与 Transformer 的推荐排序优化、用 RAG 提升商家信息覆盖率），本地生活场景的「算法-商业指标联动」考察强化（如优化 CTR 或降低司机空驶率），但经典基础（如贪心证明正确性、DP 状态转移）的工程落地能力仍是核心评判标准。
- **岗位偏好：**
  - 后端（e.g., 外卖系统、酒店预订、美团云）：贪心/DP/图（40%），变体多为「多约束优化问题」（如带时间窗的配送路径规划变体），高频题包括「最短路径的多权重适配」「子数组和的最大差值」等，业务场景如骑手派单调度、库存动态更新、云资源弹性扩容策略设计。
  - 算法岗（搜索/推荐/广告）：DP/贪心/机器学习融合（45%），侧重「业务指标驱动的算法设计」（如基于用户消费轨迹的序列 DP 推荐变体），融合特征工程（如外卖订单的时间/距离特征融入贪心状态），常考察「算法优化与商业指标的关联」（如如何用模型降低用户取消订单率）。
  - 客户端（e.g., 美团 App、大众点评）：数组/字符串/链表（35%），偏「轻量场景的高效实现」（如 O(1) 空间的本地地址解析），高频题涵盖「字符串匹配的前缀树优化」「链表的局部反转」等，业务场景如本地订单缓存的增量同步、商家地址的快速检索匹配、滑动加载性能调优。
  - 数据开发/数仓：图/DP/并行处理（42%），核心考察「海量业务数据的处理效率」（如亿级外卖订单的时序统计变体），适配 Hive/Spark 框架，业务场景如跨区域订单数据的实时聚合、用户消费行为的离线分析建模、商家营收数据的去重与关联。
 ### 改编题目
| 改编描述 | 业务场景 | LeetCode原题 |
|----------|----------|--------------|
| 给定数组，求子数组最大和。面试常问：k长子数组变体。 | 美团外卖连续订单最大收益计算 | [LC53 最大子数组和](https://leetcode.cn/problems/maximum-subarray/) |
| 给定数组和目标，求两数之和索引。面试常问：三数扩展。 | 美团支付双交易匹配 | [LC1 两数之和](https://leetcode.cn/problems/two-sum/) |
| 给定0/1网格，统计岛屿数量。面试常问：最大面积（LC695）。 | 美团商家地图聚类 | [LC200 岛屿数量](https://leetcode.cn/problems/number-of-islands/) |
| 给定数组，找出第K大元素。面试常问：实时流。 | 美团热搜商品排名 | [LC215 数组中的第K个最大元素](https://leetcode.cn/problems/kth-largest-element-in-an-array/) |
| 给定区间数组，合并重叠区间。面试常问：多区间排序。 | 美团骑手时间调度合并 | [LC56 合并区间](https://leetcode.cn/problems/merge-intervals/) |
| 给定面额和金额，求最少硬币数。面试常问：完全背包。 | 美团支付最小手续费分配 | [LC322 零钱兑换](https://leetcode.cn/problems/coin-change/) |
| 给定数组，判断等和子集。面试常问：0/1背包。 | 美团订单流量等分流 | [LC416 分割等和子集](https://leetcode.cn/problems/partition-equal-subset-sum/) |
| 给定二叉树，计算直径。面试常问：平衡检查。 | 美团配送网络树分析 | [LC543 二叉树的直径](https://leetcode.cn/problems/diameter-of-binary-tree/) |
| 给定字符串，计数回文子串。面试常问：奇偶扩展。 | 美团地址文本相似匹配 | [LC647 回文子串](https://leetcode.cn/problems/palindromic-substrings/) |
| 给定有序数组，实施二分查找。面试常问：旋转偏移（LC33）。 | 美团商品价格查询 | [LC704 二分查找](https://leetcode.cn/problems/binary-search/) |
| 给定数组，求除自身外乘积（无除法）。面试常问：O(1)空间。 | 美团商家权重统计 | [LC238 除自身以外数组的乘积](https://leetcode.cn/problems/product-of-array-except-self/) |
| 给定数组和k，求窗口最大值。面试常问：中位数（LC480）。 | 美团滑动订单评分分析 | [LC239 滑动窗口最大值](https://leetcode.cn/problems/sliding-window-maximum/) |
| 给定旋转数组，搜索目标。面试常问：重复元素（LC81）。 | 美团循环菜单ID查询 | [LC33 搜索旋转排序数组](https://leetcode.cn/problems/search-in-rotated-sorted-array/) |
| 给定字符串，生成所有有效括号组合。面试常问：n=10边界。 | 美团配置参数生成 | [LC22 括号生成](https://leetcode.cn/problems/generate-parentheses/) |
| 给定字符串，计算编辑距离。面试常问：DP空间优化。 | 美团搜索关键词补全 | [LC72 编辑距离](https://leetcode.cn/problems/edit-distance/) |
| 给定点数组和K，找原点最近K个点（欧氏距离）。面试常问：优先队列。 | 美团附近商家KNN推荐 | [LC973 K 个最近的点](https://leetcode.cn/problems/k-closest-points-to-origin/) |
| 给定点数组，计算直线上最多点数（斜率哈希）。面试常问：重合点处理。 | 美团骑手路径碰撞检测 | [LC149 直线上最多的点数](https://leetcode.cn/problems/max-points-on-a-line/) |
| 给定链表，反转整个链表。面试常问：k组翻转。 | 美团聊天记录链路处理 | [LC206 反转链表](https://leetcode.cn/problems/reverse-linked-list/) |
| 给定链表，找中间节点。面试常问：奇偶处理。 | 美团订单列表分页 | [LC876 链表的中间结点](https://leetcode.cn/problems/middle-of-the-linked-list/) |
| 给定m x n网格，计算不同路径数。面试常问：障碍物变体（LC62）。 | 美团骑手多路径规划 | [LC63 不同路径 II](https://leetcode.cn/problems/unique-paths-ii/) |
  
