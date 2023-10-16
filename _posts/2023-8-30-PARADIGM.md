---
layout: post
title: 关于常用功能分析的应用和总结二 多组学整合分析 PARADIGM
categories: Bioinformatics
description: 这是一个基于已知的pathway的结构，利用极大似然推断Pthway在个体中的活性状态，基于IPA通路激活情况聚类分型。
keywords: pathway,功能分析,分型,多组学分析
---

## I nference of patient-specific pathway activities from multi-dimensional cancer genomics data using PARADIGM


Abstart

1 技术发展带来了癌症的全面信息，copy number variation,gene expression,DNA methylation and epigenetics.分析现有数据集可以找到病人基因改变不同之，但是通常共同受到影响的 pathway.所以识别参与癌症进展的相关通路并检测它们在不同患者中的变化是至关重要的。

2 结合基因间的通路相互作用，作者提出了一种推测患者特异性遗传活动的新方法。合并多个组学数据作为证据和以基因表达，已知的产物作为变量，通过一个因子图对Gene进行建模。通过这个方法去推断哪些通路是在患者中发生了通路的活性的改变

3 作者用自己的方法与SPIA作了比较，作者在成胶质母瘤细胞和乳腺癌中推断了改变的活性通路，以及更小的假阳性。
    患者中存在不同的基因但是发现了共有的pathway水平
    分组生存分析






单词

interconnected  v.互相连接，互相联系( interconnect的过去式和过去分词)；
glioblastoma    成胶质母细胞瘤
glioblastoma multiform(GBM) 多形性胶质母细胞瘤
premise n.前提；[复数]房屋；[复数][合同、契约用语]上述各点；（逻辑学中的）大[小]前提； vt.预述（条件等）；提出…为前提；假设；作出前提；
prognosis   n.[医]预后，判病结局；预测；
diagnosis   n.诊断；诊断结论；判断；结论；
treatment regimen   治疗方案
a handful of    一些
follow-up   n.[医]定期复查，随访；跟踪；后续行动，后续事物； adj.重复的；补充的；继续的；接着的；
monoclonal  adj.单克隆的；
Apoptosis   [细胞]凋亡；
constituent n.选民；成分，构成部分；委托人； adj.构成的，组成的；选举的；有选举权的；
in place of 代替
distinct    adj.明显的，清楚的；卓越的，不寻常的；有区别的；确切的；
diagram n.图表；图解；示意图；[数]线图； vt.用图表示；图解；
information flow    信息流
concentrations  n.集中( concentration的名词复数 )；专心；关注；浓度；
factor graph    因子图  只能说将简单的蛋白质表达变为其变化情况，表示可能是一种原因。或者说问题
agreement   n.协定，协议；同意，一致；合同书；（词之间性、数、人称方面与…）一致；
Conversely  adv.相反地，颠倒地；倒地；反之；反过来；
abstained   v.戒（尤指酒），戒除( abstain的过去式和过去分词 )；弃权（不投票）；
ternary 多元
complete    adj.（用以强调）完全的；完成的；达到结尾的；完整的； vt.完成，使完满；完成或结束；填写（表格）；
inactivated .使不活泼，阻止活动( inactivate的过去式和过去分词 )；
singleton   n.一个，独身，单独；
majority    n.多数；（获胜的）票数；成年；法定年龄；
analog  n.类似物，同源语；<电脑>模拟； adj.（钟表）有长短针的；<电脑>模拟的；
permutation n.（一组事物可能的一种）序列，排列，排列中的任一组数字或文字；
tuple   n元组,列表
perturbation    n.<正>忧虑；不安；烦恼；<术>摄动；
Decoy   
regimens    n.（为病人规定的）生活规则，养生法( regimen的名词复数 )；养生之道；
paradigm    n.范例，样式，模范；词形变化表；
trastuzumab [医]曲妥单抗，群司珠单抗<抗肿瘤药>；
underlie    vt.位于或存在于（某物）之下；构成…的基础（或起因）；[经]构成优先于…的财政要求；
tumorigenesis   n.肿瘤发生；
elusive adj.难以捉摸的；不易记住的；逃避的；难以找到的；
pilot   n.飞行员；引航员；向导；[机械学]导向器（或轴）； vt.驾驶；试验；试点；为（船舶）引航（或操舵）； adj.试验性的；导向的；驾驶员的；辅助的；
consequences    n.重要（性）( consequence的名词复数 )；结果；重要地位；因果关系；
causal  adj.具有因果关系的，构成原因的；
elucidate   vt.阐明，解释；
abrogate    vt.废除（法律等）；取消；去掉；抛开； n.取消，废除；
compendium  n.摘要，纲要；
compensate  vt.补偿，赔偿；报酬；抵消； vi.补偿，弥补；



INTERDUCTION

1 现代癌症治疗的一个中心前提是，可以根据肿瘤的基因组、转录和表观基因组特征以及诊断时收集的相关临床信息对癌症进行分层，从而提高患者的诊断、预后、风险评估和治疗反应预测(通过多组学对癌症进行分型很重要)
trastuzumab [医]曲妥单抗，群司珠单抗<抗肿瘤药>；
2 现在虽然有技术但是分型效果不好，比如在25%的breast cancer中存在ERBB2独特的扩增或者过表达。只有小于50%ERBB2患者对于trastuzumab药物敏感，表明我们对于癌症pathway或者说机制的不完全理解

3 癌症是一种基因组突然发生改变的疾病,使得细胞周期失调.

4 1 这些已有的发现不同的患者虽然存在着不同的突变或者异常表达基因，但是有着共同的受影响的pathway,2已有研究表明缺失和扩增使得pathway活性同向


5 GSEA 和 hypergeometric test GO 的方法被开发用于去识别不同疾病条件下的pathwa富集分析，但是但是这些方法都没有去整合一直的Gene与Gene之间的依赖，这写方法对所有基因的处理都是一样的，所以由于这些因素，过度表现分析经常错过具有边缘性差异活性的基因的功能相关通路。

6 作者表示可以利用已知的Gene的相互作用和表型因果数据集，Reactome,NCI PID ,KEGG 三个数据库将分散在数据库中的pathway信息收集整合 .一个关键的假设是，可以利用这些路径的交互拓扑结构来解释高吞吐量数据集。但是直到最近才有一部分方法利用pathway去解释高通量的数据集---SPIA(pageRank)

7 cprobabilistic graphical model 已经被发现具有学习有因果网络的能力.可以从数据中自动学习路径(Friedman和Goldszmidt, 1997;Murphy等人，1999)，并且很好地适应了遗传网络推理中的问题(Friedman, 2004)。例如，图形模型已被用于识别在癌症生物学中形成“模块”的基因集(Segal等人，2005年)。他们也被用于阐明肿瘤基因型和表达表型之间的关系(Lee et al.， 2006)，并推断蛋白信号网络(Sachs et al.， 2005)和重组基因调控代码(Beer and Tavazoie, 2004)。特别是，因子图已被用于建模表达数据(Gat-Viks和Shamir, 2007;Gat-Viks等人，2005,2006)。

8 作者开发一个基于factor graph 的PGM框架，可以整合任意数目的基因组或者基因组功能数据集去推断患者样本的分子通路的改变.作者使用了CNV和expression的数据集，使用结构化的pathway模型成功推断了glioblastoma患者到临床学相关的亚型.也表现出相对当个Gene-level信息，pathway-information推断性能更好。同时所提供了更好的诊断和预后，为癌症提供了潜在治疗提手段


METHODS

breast cancer CNV GSE8757 匹配的 MIAMIExpress


Pathway compendium
我们提取了五种不同类型的生物实体，包括三种物理实体(蛋白质编码基因、小分子和复合物)、基因家族和抽象过程。



Pathway compendium
### \( X \) 的联合概率分布

给定一组表示细胞状态的随机变量：
\[ X=\{x_1,x_2,...,x_n\} \]

**描述**：
- \( X \) 表示细胞的整体状态，封装了所有感兴趣的随机变量或实体。
- \( X \) 中的每个 \( x_i \) 都是一个特定的随机变量（或实体），它可能对应于特定的基因、蛋白质或其他生物实体。

所有这些实体的联合概率分布为：
\[ P(X)=\frac{1}{Z} \prod_{j=1}^{m} \phi_j(X_j) \]

**描述**：

- \( P(X) \) 是 \( X \) 的联合概率分布，表示所有实体同时处于某一状态的可能性。
- 乘积项 \(\prod_{j=1}^{m} \phi_j(X_j)\) 是对所有因子 \(\phi_j\) 的乘法，它们代表这些实体之间的互动和信息流。

规范化常数定义为：
\[ Z= \sum_j \sum_{S<X_j} \phi_j(S) \]

**描述**：
- \( Z \) 确保 \( P(X) \) 是一个有效的概率分布，总和为1。
- 项 \(\sum_{S<X_j} \phi_j(S)\) 表示对 \( X_j \) 中的所有变量的所有“设置”的总和，考虑到所有可能的状态或配置。



