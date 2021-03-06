# 强化学习

它主要解决的问题是机器如何根据某一时刻的信息决定下一时刻需要采取的行动。强化学习也被运用在人工智能领域，比如说让机器人学习如何走路。机器在作出决策之后，

如果得到期望的结果，机器会得到奖励，反之则会得到惩罚。通过这个试错的过程，机器可以学到如何对已有的信息作出决策。

### [UCB](https://github.com/hanxinle/practical_machine_learning/tree/master/6_Reinforcement%20Learning/UCB)

![image text](https://github.com/hanxinle/practical_machine_learning/blob/master/6_Reinforcement%20Learning/UCB/UCB_Algorithm_Slide_cn.png)


如上图,置信区间上界算法,是迭代选择每次置信区间最大的数据,最终使得所有数据逼近自身的置信区间,最后根据置信区间最大值的来执行操作.

这一节的例子是商家投放了10个广告,每个广告代表一种商品使用场景,我们的任务是决定投放哪个广告.这个数据不仅仅是要求选中的广告的点击率最大,而且要针对第n个用

户决定投放哪个广告,从而确保该广告的点击次数是最大的,数据来源并非投放广告前的统计,而是一种模拟数据,模拟了10000个用户对每个广告的点击情况.


作为对比,同时附上随机算法对每个用户投放广告,得到每个广告被选取次数的直方统计.可以看到,随机算法说明,10000个用户对每个广告的点击数几乎是平均的,约为1000.


### [Thompson Sampling](https://github.com/hanxinle/practical_machine_learning/tree/master/6_Reinforcement%20Learning/Thompson_Sampling)

这一算法的基础是贝叶斯推断,beta分布.预测每个选择的期望,每一轮生成每个数据的期望,选择最大的return值,调整该数据的数据期望,再重新生成每个数据的数学期望,

重复上面这个步骤,频繁选择的数据会越来越窄.

与UCB算法,UCB是确定性算法,计算得到相同的置信区间上界的时候,我们永远会做出相同的决策,得到的收益也是确定的,每一轮实时更新奖励,可能会与实际情况相悖,出现

奖励偏差.Thompson抽样算法是随机性算法,允许延迟更新/批量更新,可以收集一定数量的用户数据后再更新期望,相较于UCB,能够减小遗憾出现的概率.
