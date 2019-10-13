## 各种分类模型的优点和缺点
![image text](https://github.com/hanxinle/practical_machine_learning/blob/master/3_Classification/classification%20models%20views.jpg)

## 评估分类模型的表现

    评估模型的表现,有以下几种方法:
    
* 伪阳性和伪阴性False Positives & False Negatives

    伪阳性又成为I型错误,伪阴性被成为II型错误,在实际情况中,II型错误导致的后果要比I型错误严重,比如说在疾病检测中,将患病个体检测为健康个体,会造成更加严重的后果,如耽误治疗\加快疾病传染.
  
* 混淆矩阵 Confusion Matrix

    行代表预测值,列代表真实值,对角线上的数字是每个标签的预测正确的数量,通过全部的元素,可以计算得到总体的正确率.但是混淆矩阵有个陷阱,在某一类别数据过多时,将所有的预测值都设置为与之相同,这种做法依然会使模型的正确率看起来很高,实际上并非如此,为了避免这种情况,需要其它对模型信息描述更加先进的方法.
    
* 累积准确曲线 CAP Curve

    一个凸曲线,横轴代表对样本的采样率,纵轴代表某事件的发生率,它的横轴概念上与ROC曲线是一样的,CAP还没有维基百科上定义.CAP上判断模型的性能的方法是,用其与随机模型的面积与水晶球曲线的面积做壁纸,随机模型的形状是过原点的斜率为正的直线.一个更加直观的方法是取X轴5为50%时,看Y轴的对应值,<60%:不好,60%-70%:poor,70%-80%:good,80%-90%:very good,90%-100%:too goood,需要注意的是,此时正确率大于90%,一种情况是自变量与因变量有强关系,另一种则是过拟合.当然,这种情况也可能是由于数据质量高,及模型选择得当.
   
   
## 对于每个不同的案例，我如何在这些模型中作出选择？

       首先，您需要判断您面对的是一个线性还是非线性的问问题,后续过程中会涉及模型选择内容,接下来：

       假如是线性的问题，您应该选择逻辑回归（logistic regression）或者支持向量机SVM。
       假如是非线性的问题，您应该选择朴素贝叶斯（naive bayes），决策树（decision tree）或者是随机森林（random forest）。在接下来的课                     程中我们会讲到神经网络（neural network），也是一个十分强大的方法。
       然后，在每种情况下，应该如何选择分类模型呢？您会在第10部分的K次交叉验证（k-fold cross validation）中学到。

       现在，从实际操作的角度来说，您可以大致遵循以下的规则：

       假如您想要给最终预测概率进行排序，您应该选择逻辑回归（logistic regression）或是朴素贝叶斯（Naive Bayes）。举个例子：您想要预测不同客户购买某项产品的概率，并将这些概率从大到小进行排序，以便锁定目标客户群。在这样的情形下，如果您的问题是线性的，您应该运用逻辑回归（logistic regression）；假如您的问题是非线性的，您应该选择朴素贝叶斯（naive bayes）模型。
       假如您想要预测每一个客户属于哪一个划分（segment），您应该选择SVM。市场和客户群体的划分可以是已完成的市场调研或者集群分析（clustering）的结果。
       假如您想要非常直观地展示／阐述模型，那么决策树（Decision Tree）是最佳选择。
       假如您想要最好的模型的分类表现，并且不太在意模型的展示／阐述，那么随机森林（random forest）是不错的选择。


## 我如何提高每个模型的表现？

       接下来的内容会涉及如何调整模型参数，以提高模型的表现。总体来说，每个模型都有两种类型的的参数：

       可以被“学习”的参数，比如：线性回归中各个自变量的参数。
       难以被学习的“超参数” （hyperparameter）。
       一个好的“超参数“的例子是随机森林（random forest）算法中训练决策树的个数N。目前为止，我们应用它的默认值（比如500）。