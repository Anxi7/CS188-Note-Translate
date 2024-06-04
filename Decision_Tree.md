# Decision Tree

## What is a Decision Tree?

决策树是一个用于做决策或预测的类似于流程图的结构。它由代表决策或属性测试的节点、代表这些决策的效果的分支以及代表最终结果或预言的叶节点构成。

每个内节点对应于一个对某个属性的测试，每个分支对应于测试的结果，每个叶节点对应于一个类标签或一个连续值。

## Structure of a Decision Tree

1. 根节点：表示整个数据集和要做出的初始决策。

2. 内部节点：代表决策或属性测试，每个内部节点有至少一个分支。

3. 分支：代表决策或测试的结果，通向另一个节点。

4. 叶节点：代表最终的决策或预言，在这些节点上没有进一步的分支。

## How Decision Trees Work?

构建决策树的过程涉及以下几步：

1. 选择最优属性：使用基尼不纯度（Gini impurity）、熵（entropy）或信息增益（information gain）等度量，选择分割数据的最佳属性。

2. 分割数据集：基于选择出的属性将数据集划分为子集。

3. 重复上述过程：对每个子集递归地重复这个过程，创建一个新的内部节点或叶节点，直到满足停止条件。（例如：节点中的所有实例属于同一个类或者达到了预定义的深度）

## Metrics for Splitting

- Gini Impurity
  - 如果根据数据集中类的分布对新实例进行随机分类，则度量新实例分类错误的可能性。

  - Gini = $1 - \sum_{i = 1}^{n}(p_i)^2$
    - 其中 $p_i$ 是实例被分类到特定类的概率。

- Entropy
  - 度量数据集中不确定性或杂质的数量（the amount of uncertainty or impurity）

  - Entropy = $-\sum_{i = 1}^{n}{p_i \log_2(p_i)}$
    - 其中 $p_i$ 是实例被分类到特定类的概率。

- Information Gain
  - 度量基于某属性划分数据集后的熵或 Gini impurity 的减少量

  - $InformationGain = Entropy_{parent} - \sum_{i = 1}^{n}\left(\frac{|D_i|}{|D|} \times Entropy(D_i)\right)$
    - 其中 $D_i$ 是 $D$ 基于某属性划分后的子集。

## Pruning

可以使用剪枝技术避免过拟合。剪枝通过去除在分类实例方面能力不足的节点来减小树的大小。有两种主要的剪枝类型：

1. Pre-pruning (Early Stopping)：一旦达到特定标准就停止树的增长（例如：最大深度，每个叶节点的最小样本数）

2. Post-pruning：从一棵已经生成好的树上去除不能提供显著帮助的分支。

## Decision Tree in Machine Learning
