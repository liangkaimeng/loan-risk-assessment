# loan-risk-assessment
借贷风险评估[迁移学习]



比赛地址：https://www.heywhale.com/mw/project/5ca1e8498408c1002b4880be/content

赛题描述：

- 给定的4万条业务A数据及4千条业务B数据，建立业务B的信用评分模型。其中业务A为信用贷款, 其特征是债务人无需提供抵押品，仅凭自己的信誉取得贷款，并以借款人信用程度作为还款保证；业务B为现金贷，即发薪日贷款（payday loan），与一般的消费金融产品相比，现金贷主要具有以下五个特点：额度小、周期短、无抵押、流程快、利率高，这也是与其借贷门槛低的特征相适应的。
- 由于业务A、B存在关联性，选手如何将业务A的知识迁移到业务B，以此增强业务B的信用评分模型。

  

# 迁移学习与冷启动

## 冷启动

冷启动是指在没有或只有很少量数据的情况下，从0到1建立业务模型的过程。在风控业务中，早期缺乏数据积累，迁移学习和异常检测技术都可以用来处理部分冷启动问题。

## 应用场景

- 新开了某个业务，只有少量样本，需要用其他场景的数据来建模。此时其他场景为源域，新业务场景为目标域。
- 业务被迫停止3个月后重启，大部分训练样本比较老旧。大部分旧样本为源域，新的少量训练样本为目标域。
- 在某个国家开展类似国内的业务。国内业务积累的数据为源域，新国家场景为目标域。

　概括起来，源域样本和目标域样本分布有区别，目标域样本量又不够。

## **TrAdaBoost模型**

　将不同分布的训练集放在一起训练，这种方法也叫作基于实例的迁移学习方法。
　TraAdaBoost是有AdaBoost演变而来。在一个包含源域训练数据和目标域样本的训练集中，TrAdaBoost会对训练样本进行权重调整。

- 对目标域样本，如果被误分类，根据目标域样本的分类错误率进行调整，增加其权重，使得下次训练时更关注错分的目标域样本。
- 对源域样本，如果被误分类，则会认为它们是与目标数据不同分布的，会降低其权重。



















