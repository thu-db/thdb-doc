# 基础功能

## 任务 1：选择算子下推（5 分）

### 实验描述

补全优化器 Optimizer 类中关于选择和连接算子下推的相关函数，实现算子下推功能。

### 实现思路

-   步骤 1：补全 PushDownFilter 函数，根据 Filter 条件判断算子为选择算子还是连接条件算子，并记录到成员变量中。

-   步骤 2：补全 PushDownSeqScan 函数，根据步骤 1 记录的选择算子调整扫描算子的结构，添加对应的过滤条件。

-   步骤 3：补全 PushDownJoin 函数，根据步骤 1 记录的连接条件算子调整连接算子的实现方式，将原始的笛卡尔积算子优化为根据条件连接算子。

## 任务 2：基于贪心算法的连接顺序选择（10 分）

### 实验描述

补全优化器 Optimizer 类中 ReorderJoin 函数以及数据库 Analyze 功能，实现数据表信息统计、基数估计以及连接顺序选择。

### 实现思路

-   步骤 1：补全直方图类的生成以及查询函数，用于后续的基数估计。

-   步骤 2：补全数据库 Analyze 功能，实现数据表的信息统计功能，需要调用直方图的生成函数并正确存储到系统表 statistic 表中。

-   步骤 3：补全 Optimizer::JoinReOrder 函数，补全连接顺序选择算法，使用贪心算法实现这一过程。