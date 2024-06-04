# Machine Learning

在这门课之前的 Note 中，我们学习了能帮我们在不确定情况下 *推理*（reason）的各种模型。直到现在，我们一直认为我们使用的概率模型（probabilistic models）是理所当然的，并且我们使用的生成底层概率表（probability table）的方法已经被抽象掉了。

当我们深入讨论机器学习时（machine learning），我们将开始打破这个抽象障碍。机器学习是计算机科学中的一个广泛领域，它处理给定一些数据的特定模型的 *构造和（或）学习参数问题*。

根据机器学习算法希望完成的任务和处理的数据类型的不同，可以将其分为多种。其中两种主要的子类型是 **监督式** 学习算法（supervised learning algorithms）和 **无监督式** 学习算法（unsupervised learning algorithms）。

监督式学习算法推断输入数据和对应输出之间的关系，以便预测新的、从未见过的输入数据的输出。而无监督式学习算法的输入数据没有任何对应的输出数据，因此需要识别数据点之间和数据点内部的固有结构，并根据这些结构对其进行分组和（或）处理。

在这门课上，我们讨论的算法仅限于监督式学习任务。

> 监督式学习和无监督式学习的经典例子是：分类和聚类。前者将数据分为不同的类，这些类在事先是已知的；而后者也是将数据分为不同类，但这里的类在事先未知。
>
> 因此，我们也可以说监督式和无监督式学习的主要区别是有无标签（label）！这里的标签指的是类标签，用于标识不同的类。

一旦你有了一个准备用于学习的数据集，机器学习过程通常涉及将数据集分为三个不同的子集。其一是 **训练数据**（training data），用于实际生成一个将输入映射到输出的模型。其二是 **验证数据**（validation data，也被称为保留数据 hold-out data 或开发数据 development data），用于通过预测输入并生成一个准确度评分来衡量模型性能。

如果你的模型没有像你希望的那样表现得很好，你可以回去重新训练，或者通过调整被称为 **超参数**（hyperparameter）的特殊模型特定（model-specific）值，或者使用一个完全不同的学习算法，直到你对你的结果满意。

最后，使用你的模型对数据的第三个也是最后一个子集 - **测试集**（ test set）进行预测。测试集是智能体在开发结束之前从未见过的那部分数据，相当于在真实世界中的数据上衡量性能的 “期末考试”。

> - **训练集（Training Set）**：模型用来学习的数据集。模型通过反复调整参数来拟合训练集中的数据。这部分数据用于直接训练模型。
>
> - **验证集（Validation Set）**：用于评估模型在训练过程中的性能。验证集的数据不用于训练模型，而是用于调整超参数和选择模型，以确保模型不会过拟合。验证集提供了对模型在训练数据之外的性能的评估。
>
> - **测试集（Test Set）**：用于最终评估模型性能。这部分数据是完全独立的，既不用于训练模型，也不用于调整超参数或选择模型。测试集的数据用于对最终模型的泛化能力进行无偏估计。
>
> 这三部分数据在理想情况下应该是互相独立且没有重叠的：
>
> - **训练集**：用于训练模型。
>
> - **验证集**：用于模型的调优和选择，确保模型在训练数据之外的良好表现。
>
> - **测试集**：用于最终评估模型，确保模型能够在未见过的数据上表现良好。
>
> 这种数据划分方法有助于评估模型的实际性能，确保模型具有良好的泛化能力，并防止模型过拟合。

在接下来的内容中，我们将介绍一些基本的机器学习算法，如：朴素贝叶斯、线性回归、逻辑回归和感知器算法（Naive Bayes, Linear Regression, Logistic Regression and the Perception algorithm）。

## Naive Bayes