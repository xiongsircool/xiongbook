---
layout: post
title: RNAincoder a deep learning-based encoder for RNA and RNA-associated interaction
categories: Bioinformatics
description: 作者开发了RNAincoder(deep learning-based encoder for RNA-associated interactions) 其目的是(a)提供RNA编码特征的全面集合，（B）基于完善的深度学习的嵌入策略实现任何RNA相关相互作用的表示（c）能够大规模扫描所有可能的特征组合，以识别RNA相关相互作用预测中的最佳性能之一4 结论:通过对基准数据集的案例研究，广泛验证了RNAincoder的有效性。
keywords: AFTGAN,RNA,interaction , 生物信息方法
---



## RNAincoder a deep learning-based encoder for RNA and RNA-associated interaction

背景
1	核糖核苷酸通过与蛋白质和化合物以及其他RNA相互作用 参与到不同的生物或病理的过程。
2 	当前已经有大量强有力的计算方法被开发用于预测有价值的相互作用。然而这些方法严重依赖RNA相互作用对的数字化(encoding方式)为计算机可识别描述符。换句话说，现在迫切需要有一个强大的工具，它不仅可以表示每个交互的伙伴，而且可以将两个伙伴整合到一个计算机可识别的交互中
3	因此作者开发了RNAincoder(deep learning-based encoder for RNA-associated interactions) 其目的是:
(a)提供RNA编码特征的全面集合，（B）基于完善的深度学习的嵌入策略实现任何RNA相关相互作用的表示（c）能够大规模扫描所有可能的特征组合，以识别RNA相关相互作用预测中的最佳性能之一
4 结论:通过对基准数据集的案例研究，广泛验证了RNAincoder的有效性。所以RNAincoder是一个在提供RNA有关相互作用有关的更准确表示展示出卓越能力的工具，其可以作为其他可用工具的一种补充
RNAincoder can be accessed at https://idrblab.org/rnaincoder/

![image-20230515155425446](https://raw.githubusercontent.com/xiongsircool/xiongbook/master/posts/assets/image-20230515155425446.png)

单词

pathological adj.[医]病理学的；由疾病引起的；病态的，疾病的；
physiological adj.生理学的；生理的；
descriptor n.描述符；
Herein adv.此中，于此；焉；
realize vt.实现；了解，意识到；（所担心的事）发生；以…价格卖出； vt.& vi.变卖，赚得；
effectiveness n.有效，有力；有效性；效益；效用；
distinguished adj.卓越的；著名的；受人尊敬的；显得重要的； v.辨别，区别( distinguish的过去式和过去分词)；突出；区别(distinguish的过去式)；
catalytic adj.接触反应的；起催化作用的； n.催化剂；刺激因素；
momentum n.[物]动量；势头；动力；要素，契机；
So far 到目前为止
standalone	n.脱机； adj.单独的，独立的；
merely	adv.仅仅，只不过；只是；纯粹；全然；
intrinsic	adj.固有的，内在的，本质的；[解剖]体内的；本征；先天性；
physicochemical	n.物理化学的；
subdivided	v.再分，细分( subdivide的过去式和过去分词 )；
Specifically	adv.特有地，明确地；按种别地；按特性地；
pseudopotential	赝势；
dication	双阳离子；
To be specific	具体来说
hydrophobicity,	疏水性；
polarity	n.[物]极性；[生]反向性；对立；[数]配极；
polarizability	n.极化性，极化率，极化度；可极化性；
solvent	n.[化]溶剂，溶媒；解释，说明；解决方法；使瓦解的东西； adj.有溶解能力的，可溶解的；有清还债务能力的；起瓦解作用的；
upward	adj.向上的，上升的；升高的； adv.向上地，上升地；
discriminative	adj.有判别力；
stereo	adj.立体声的；有立体感的； n.立体声；立体声系统；铅板；立体系统或立体像片；
gravitational	adj.万有引力的，重力的；地心吸力的；
breadth	n.宽度；宽容；（知识、兴趣等的）广泛；
inertia	n.<物>惯性，惰性；迟钝；不活动；
radial adj.辐射状的；放射式的；径向的；星形的； n.子午线轮胎，辐射状轮胎；
aqueous	adj.水的，水成的；
solubility	n.溶解度；可解决性；溶度；
outstanding	adj.杰出的；显著的；凸出的；未完成的；





## 介绍

Ribonucleic acids (RNAs)主要的功能是基因表达的催化分子以及在调节不同生物学功能或病理进程中扮演着一个基础角色。大量研究表明RNA与RNA，蛋白质，compounds存在相互作用，且在RNAs‘ 功能中至关重要。相关的研究产生大量的动力，同时催生了开发大量高效的方法去预测有价值的相互作用.所有的这些方法都是依赖于将RNA有关的相互作用数字化为计算机可识别的语言，这也使得开发的工具具有数字化RNA，蛋白质，以及compounds的能力。

到目前为止，已经构建了各种旨在准确和有效地数字化不同类型分子的方法/工具:
1	PROFEAT是一个广泛使用的Web服务器，可以计算蛋白质和肽的流行描述符的总共11个特征组

2	PseKRAAC已被开发用于产生各种假氨基酸组合物

3	PaDEL-Descriptor 计算797个分子描述符和10种类型的指纹与多种常用的用户界面

4	Mordred 是一个分子描述符计算器，可生成>1800个描述符

5	PyDPI和Rcpi是用于计算蛋白质和小分子特征以研究蛋白质-蛋白质相互作用和复合蛋白质相互作用的独立软件包

以上方法或者说现存的工具一些主要是集中于编码一种类型的分子比如蛋白质，RNA，或者化合物，而另一些仅仅常用于编码蛋白质和化合物之间的相互作用。然而，目前没有编码RNA相关相互作用的工具。此外，据我们所知，编码RNA的服务器中的编码策略远不全面。换句话说，迫切需要有一个强大的工具来研究RNA相关的相互作用，它不仅可以描述RNA及其相互作用的伴侣，而且还可以将两种分子整合到一个相互作用对中。然而，目前还没有这样的工具。

在此，因此提出了RNAincoder以用于（a）提供RNA编码特征的全面集合（包括序列内在的、物理化学的和基于结构的），（B）基于完善的基于深度学习的嵌入策略实现任何RNA相关相互作用的表示，以及（c）能够对所有可能的特征组合进行大规模扫描，以鉴定RNA相关相互作用预测中的最佳性能之一。在本工作的最后一节中，通过三个案例研究广泛展示了RNAincoder的有用性。总而言之，当与原始出版物中应用的策略相比时，RNAincoder始终实现了RNA相关相互作用的更好预测性能

## 方法和材料

### Collection of the comprehensive strategies for encoding RNA 

收集了常用于RNA编码过程中的380RNA 描述符并整合到RNAincoder中为10个编码特征分组--177个序列的固有特征分成6个groups，195个理化特征细分到3个group,8个基于结构的特征属于一个特征组.

​	sequence-intrinsic：codon related (CDR), open read-ing frame (ORF), guanine–cytosine related (GCR), K-mer(KME), 	global descriptor (GBD) and entropy density related (EDT).密码子有关的,开放读码框,GC相关的,k-mer,全局的描述,熵	密度相关。在CDR中Fickett score[CDR]在评估RNA为长链非编码RNA上具有94%敏感性和97%特异性。该ORF是一个	可行的和有意义的RNA特征组，因为蛋白质编码转录本的长和高质量的ORF.KME是通过k个相邻核酸的出现频率编RNA       序列的简单方法，并且已成功应用于ncRNA的功能分类.此外，GCR、GBD和EDT在RNA预测（28）、分类（7）和注释 中显示出有效的增强

Physicochemical features: 该描述符是与RNA以和其产物有关的描述符. Electron-ion interaction pseudopotential (EIIP) based spectrum features (EBS)[核苷酸中的电子结构信息。]，nucleotide related (NTR)，pseudo protein related (PPR).比如计算dinucleotide的自相关性，伪二核酸（表示核酸序列特征的方法 ）PseDNC结合了三个角度参数（扭转、倾斜和滚动）和三个平移参数（移位、滑动和上升）的理化特征。EIIPd值可以表示核苷酸的电子-电离状态8个特征。PPR(8个)的特征组成由两步计算得到 ：1 根据遗传密码将所有RNA序列转化为相应的氨基酸序列或假蛋白序列。2 根据遗传密码将所有RNA序列转化为相应的氨基酸序列或假蛋白序列。用于反映RNA序列中的相关性和多样性

- 扭转（twist）：是指相邻两个核苷酸之间的旋转角度，即DNA/RNA双螺旋的扭转弯曲程度。
- 倾斜（tilt）：是指相邻两个核苷酸之间的平面夹角，即DNA/RNA双螺旋的侧向弯曲程度。
- 滚动（roll）：是指相邻两个核苷酸之间的平面旋转角度，即DNA/RNA双螺旋的轴向扭曲程度。
- 移动（shift）：是指两个相邻核苷酸之间在螺旋轴方向上的平移距离。
- 滑动（slide）：是指两个相邻核苷酸之间在螺旋面上的平移距离。
- 上升（rise）：是指两个相邻核苷酸之间的垂直距离，即DNA/RNA双螺旋的轴向间距

Structure-based feature：已经建立好的RNA二级和三级结构描述，对于许多RNA功能的描述是必不可少的。RNA二级结构可以用点括号表示。因此，基于结构的特征对RNA表示至关重要。

### Collecting the strategies for encoding protein and compound

​	蛋白质: RNAincoder 188个编码特征(20个固有序列特征,147理化特征和21个基础结构特征)序列特征为氨基酸矩阵，研究中涉及的物理化学特征基于电荷、疏水性、极性、极化性、溶剂可及性、表面张力和范德华体积（指分子中非共价键原子的体积总和）。这些描述符基于8种理化特征并且被应用去蛋白质精氨酸甲基化分析。基于结构的特征描述了氨基酸和肽的结构特征。这些描述符主要基于二级结构和相关的溶剂可及性，这些描述符已用于使用机器学习模型预测蛋白质-RNA相互作用

​	复合物特征: 基于之前发布的文献，将描述符分为三类。一共 2756 descriptors(1444 composition topology descriptors, 431 stereo-structural descriptors and 881 small molecules PubChem fingerprints)

## Deep learning-based embedded feature integration

RNAincoder由堆叠的变分自编码器组成。变分自编码器被应用于无监督学习有效数据表示，其包括三层；输入层，隐藏层和输出层。

RNAincoder利用三层变分自编码器构成，从编码的RNA和RNA相互作用分子特征中提取。嵌入特征训练分为三步:1)前馈算法RNA编码的特征训练AE1，得到隐藏层1的特征以及第一层。然后利用该隐藏层训练第二哥变分编码器得到隐藏层2.利用这种方式再训练第三层隐藏层 2)将第一第二第三隐藏层和一个分类器组合为SAE。然后这个SAE根据训练集的label进行微调和更新。

SAEs 用来分别提取RNA以及RNA相互作用分子的嵌入特征。并每一个AE采用全连接层来实现压缩和还原的过程。最终RNA和RNA相互作用分子的嵌入层特征链接，提供给下游的分类器(机器学习算法 随机森林,支持向量机, extreme gradient boosting，深度学习模型(RNN和CNN))去预测RNA有关的相互作用

RNAincoder的评估 ROC-AUC，马修思相关系数MCC,准确度ACC,精密度PRE,特异性SP,灵敏度SN。通过单因素ANOVA和Dunnett事后检验计算统计学显著性评估。统计学显著性用 *P< 0.05表示;**P< 0.01; ***P<0.001;****P < 0.0001。



![image-20230515191255054](https://raw.githubusercontent.com/xiongsircool/xiongbook/master/posts/assets/image-20230515191255054.png)
