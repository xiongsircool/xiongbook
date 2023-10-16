## An extensive benchmark study on biomedical text generation and mining with ChatGPT

### 摘要

动机: 经年来自然语言处理技术和硬件的提升，chatgpt3.5 和 chatgpt4 在自然语言理解和推理上有着极好的性能表现。研究者对GPTs 也进行了大量的测试并获取了极好的结果。

结果：作者对ChatGPT在生物医药语料上进行了全面的基准测试。包括文章摘要,疾病性状描述，以及生物医药的问题等。ChatGPT got a BLURB score of 58.50 while the state-of-the-art model had a score of 84.30.

一系列的实验测试证明ChatGaP 在文本理解，推理以及生成上有效性和多样性，但是对于GPT-3.5也是存在限制。



### 单词

hardware	n.五金器具；计算机硬件；武器装备；

reasoning	n.推理，论证；运用思考、理解、推想等能力的做法或过程；论究，论断； v.推理，思考；争辩；说服； adj.推理的；有关推理的；

versatility	n.多才多艺；多用途；可转动性；易变；

effectiveness	n.有效，有力；有效性；效益；效用；

pros and cons	利弊

gigabytes	n.十亿字节(giga-为字首，意为“十亿”)( gigabyte的名词复数 )；

coherent	adj.一致的；连贯的；条理分明的；清楚明白的；

versatile	adj.（指工具、机器等）多用途的；多才多艺的；有多种学问、技能或职业的；多功能的；

paragraph	n.段落；分段符号； vt.将…分段；写短文报导；

featurization	特制（影）片；特征

frozen	adj.冷冻的；冰封的；冻硬的；呆若木鸡的； v.结冰（ freeze的过去分词）；冷藏；冻结；冻住；

dialogue	n.对话；（文学、戏剧、电影等中的）对话；对白；意见分歧者之间的意见交换； vt.用对话表达； vi.对话；进行非正式的意见交换；

engage	vt.吸引住；聘用、雇佣；与…交战；使全神贯注、引起注意； vi.与…建立密切关系；衔接；参与；紧密结合；

instruction	n.授课；教诲；传授的或获得的知识，课程；[计算机科学]指令；

mentioned	v.提到( mention的过去式和过去分词 )；说起；提名表扬；传令嘉奖；

Intervention	n.介入，干涉，干预；调解，排解；

aspire	vi.渴望，立志，追求；〈诗，古〉登，升，高耸；

punctuation	n.标点法；标点符号；标点符号的使用；点标点； 

adverb	n.<语>副词；

symptom	n.症状；征兆；

Formally	adv.正式地；正规地；拘泥形式地；形式上；

pharmaceutical	adj.制药的，配药的； n.药物；

terminology	n.专门名词；术语，术语学；用辞；

procedure	n.程序，手续；工序，过程，步骤；诉讼程序，（议会的）议事程序；〈罕〉进行；

predefined	[计][修]预定义；

### 介绍

1 随着NLP的发展，一个最大的进步为Generative Pretrained Transformer(GPT)模型，其通过预训练然后再微调应用于下游任务去生成类人类的语言。

2 NLP技术已经证明了革命性的研究和临床实践的潜力。然而，生物医学语言的复杂性和巨大的数据量仍然使得开发用于文本生成和挖掘的鲁棒模型成为一项具有挑战性的任务。

3 首先，我们将概述生物医学文本挖掘的相关工作，并强调当前方法的优势和局限性;其次，将描述ChatGPT模型及其在NLP中的应用。第三，我们将讨论本研究中进行的基准测试和实验方案;最后，我们将介绍ChatGPT在各种生物医学文本生成和挖掘任务中的性能沿着其他基线生物医学NLP模型，并讨论ChatGPT在生物医学研究和临床实践中的潜在应用和未来方向。

4 这篇文章旨在去探索ChatGaP在自然语言生成和挖掘生物医药文本的性能。比较了ChatGPT 和其他最先进的生物医药模型在生物医药有关的NLP 基准数据集上的性能。挖掘ChatGPT在生物医药数据上的利弊帮助开发性能更强的NLP模型



### 背景和相关工作

由于大量医学文本数据的产生，NLP技术获得了很大的关注。而生物医药的文本挖掘算是NLP领域的一个小的研究分支(从结构的或者非结构的文本数据中提取出，分析或者总结和挖掘具有意义的信息)。通常文本挖掘是一个需要大量人力的工作，因此自动化的文本生成和挖掘能够大大的帮助研究者提取挖掘大量生物医药文献中的有意义的信息。

最近NLP领域进步最大的模型是LLM模型的开发(其有着最大的参数(数亿))





### 数据集和方法

#### Prompt design

在三个数据集（ChemProt，DDI，GAD）中，我们尝试了两种类型的提示，一种简化，一种复杂。为了阐明这两种类型提示的设计，表1中显示了生物医学关系提取任务（DDI数据集）中的一个示例。此外，对于标签的解释，还提供了一个示例答案。我们设计复杂提示的目的是为ChatGPT提供额外的指导，以更好地理解问题和答案的标签。