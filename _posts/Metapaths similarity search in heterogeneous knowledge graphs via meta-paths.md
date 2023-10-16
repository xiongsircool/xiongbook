

## Metapaths: similarity search in heterogeneous knowledge graphs via meta-paths

### 摘要

1 异质性知识图谱能够实现从遗传相互作用图谱，蛋白质相互作用网络到表示药物，疾病，蛋白质，副作用的相互作用网络的建模。

2 KGs中的分析方法依靠的节点之间的相似性,但是我们要去考虑节点和边的类型，如果关系类型的集合(meta-paths)

3 作者发布了 meta-paths 的R包能从KG的边和邻居列表计算一对节点之间的相似性指标。

4 作者在开源医学KG上复现了药物与疾病的相关关系，并且这个方法展现出良好的拓展性。


### 单词
meta-path 元路径

destination	n.目的，目标；目的地，终点；[罕用语]预定，指定；

ecosystem	n.<生>生态系统；

precomputed	adj.预先计算的；

traversal	n.横越，横断物，（横向）往返移动；

recursively	[计] 递归地；

auxiliary	adj.辅助的；备用的，补充的；附加的；副的； n.助动词；辅助者，辅助人员；附属机构，附属团体；辅助设备；


### 介绍

细胞之间相互作用，单细胞相似性网络，基因表达网络，以及病人之间交互网络都是在生物系统常见的关系型数据可以利用图的结构表示。A simple graphG=(V,E) is defined by a set of nodes V and edges E of a single type.但是真实世界的网络是多模态的，例如在一个包含蛋白质，药物，疾病的节点类型网路中其关系为“is indicated for,” “is therapeutic target of,” or “physically interacts with”。

作者这里用数学公式表示了 a single multigraph (KGs)(多重图包含多种类型的节点和边，这些节点和边可以具有多样的类型和属性) 的数学表示

G=(V,E)
\(A\) is the set of node types with a mapping function \(u: V \to A\)
the edges \(E\) of a KG can be represented as a set of tuples \((u, v)\),
where nodes \(u, v \in V\) are connected by an edge, and each belongs to a specific node type \(u \in A\) and \(v \in A\).


网络相似性建模：在知识图中，实体（如疾病、药物、蛋白质等）之间的关系通常使用网络相似性进行建模。这意味着通过分析实体之间的连接路径或链接路径来度量它们之间的相似性。

链接路径：链接路径是在知识图中的节点之间形成的连接序列。例如，如果考虑一个生物相互作用网络，其中包括疾病、药物、蛋白质、蛋白功能和副作用等节点类型，那么链接路径可以是从药物到疾病到蛋白质的序列。

相似性搜索的挑战：文本中指出，进行有意义的相似性搜索在知识图中需要考虑不同类型的链接路径。举例来说，如果考虑从药物到疾病到蛋白质的路径（RDP）和从药物到副作用到蛋白质的路径（RSP），经典的基于随机游走的相似性度量无法区分它们。虽然这两个路径长度相同，但前者考虑了与疾病相关的关联，而后者考虑了副作用机制，因此它们在生物学上有不同的含义。










### 补充

