# 集群(clustering)算法


集群（clustering）与分类（classification）虽然有许多相似之处，它们的核心思想大有不同。在集群中，我们并没有对数据的预期，也缺乏对数据结构的了解；我们的目标是把数据分成不同的群或类（cluster），使得在同一个类中的数据都有相似的属性。集群算法可以探测出人类直觉难以体察到的数据结构，并将其直接运用于集群聚类。


这部分介绍一个算法:[K均值聚类算法(K means clustering)]().

K均值聚类算法的步骤是:

(1)选择K作为数据的类别个数;

(2)随机选择K个点作为初始化的中心点,这些点不一点要来自与数据集,可以是随机的点,每个中心点可以作为一个类别.

(3)计算数据集中每个数据到各中心点的欧式距离,它的类别与离它最近的中心点的类别一致.经过这一步,每个数据都已经分类,属于K个类别中的一个.

(4)根据上述步骤得到的每个数据的分类,重新计算每个数据分类的中心点,接着重新计算每个数据的分类,重复这一步骤,直到每个数据的种类不再发生变化.

K-means算法有个初始中心点的选择陷阱,初始中心点的随机选取,会导致同样的数据的分类结果不同,现在提出了Kmeans++算法,并且已经集成到了常用的开发

包.这个算法是指,在选取了不同的K值应用了K-means算法以后,计算组内平方和,即∑(每个类的数据到其中心点的距离),观察组内平方和的变化,画出中心点个数K

和组内平方和的函数图像.选择曲线手肘的速度,即组内平方和下降迅速到缓慢的转折点,将这个点所在的X轴数值K作为K-means算法的类别数量.


本章提供大型购物商场的客户信息,说明了客户的年收入和客户的购物指数,需要据此对顾客进行分类,拥有了对顾客类别的分类数据,就可以帮助商场进行经营上的

决策,如确定目标顾客所在的群体,并且将促销活动向这一目标群体的购物习惯调整.