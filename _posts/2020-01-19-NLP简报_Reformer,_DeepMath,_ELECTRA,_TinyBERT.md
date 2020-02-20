---
layout: post
title: "NLP简报: Reformer, DeepMath, ELECTRA, TinyBERT for Search, VizSeq, Open-Sourcing ML,…"
author: billy_rick
modified:
comments: true
excerpt: ""
tags: [nlp_newsletter]
image:
  thumb: nlp_newsletter_2.png
---


![](https://cdn-images-1.medium.com/max/1200/1*mgWc3FhHPRfCxdPir6wSeg.png)

\\
*Thanks to* [*Kaiyuan*](https://blog.csdn.net/Kaiyuan_sjtu) *(WeChat: NewBeeNLP) for this great translation.*

\\
欢迎回到 NLP 简报第二期！**如果想让自己有趣的研究/项目出现在 NLP 简报中，随时在公众号后台留言联系我**

\\
来看看本期的内容，

- **1、Publications 📙**
    - 1.1 关于信任模型的不确定性
    - 1.2 Systematic generalization
    - 1.3 Reformer
    - 1.4 用于文本分类的无监督域自适应
    - 1.5 改进的上下文表示
    - 1.6 模型可解释性
- **2、Creativity and Society 🎨**
    - 2.1 情感不匹配
    - 2.2 多巴胺的理解和蛋白质折叠
    - 2.3 有关ML的访谈
- **3、Tools and Datasets ⚙️**
    - 3.1 生产环境中的PyTorch模型
    - 3.2 可视化文本生成序列
    - 3.3 效果最优的在线语音识别
- **4、Ethics in AI 🚨**
    - 4.1 AI implications
    - 4.2 现代自然语言处理的环境成本
- **5、Articles and Blog posts ✍️**
    - 5.1 开源ML
    - 5.2 计算机视觉的自监督学习
    - 5.3 用于搜索的TinyBERT
    - 5.4 主动转移学习
    - 5.5 Revealing the Dark Secrets of BERT
- **6、Education 🎓**
    - 6.1 Neural Nets for NLP
    - 6.2 深度学习数学
    - 6.3 Python课程和教程
    - 6.4 Deep Learning State of the Art
    - 6.5 在线学习和研究
    - 6.6 The landscape of Reinforcement Learning
- **7、Noteworthy Mentions ⭐️**


# 1、Publications 📙

**1.1 关于信任模型的不确定性**

\\
来自 Google AI 的最新论文Can You Trust Your Model's Uncertainty?[1]发表在 NeurIPS 上，研究的是模型的概率是否反映了其预测分布失调和数据移位的能力。发现深度继承模型在数据集移位上表现更好（即改进了模型不确定性），而其他模型并没有随着数据集移位变得越来越不确定，而是确信地变成了错误。可以查看官方博客[2]了解更多。

\\
![](https://cdn-images-1.medium.com/max/800/0*NrsUnHS1thKq3ChK.png)

\\
**1.2 Systematic generalization**

\\
ICLR 上发表的一篇有趣的工作：<Systematic Generalization: What Is Required and Can It Be Learned?[3]>提出了模块模型和通用模型之间的比较，以及它们在语言理解中进行系统概括的有效性。基于对视觉问题回答任务进行的推理评估，作者得出结论，可能需要明确的正则化函数和先验知识才能实现系统的概括。

\\
**1.3 Reformer**

\\
众所周知，由于在 attention layer 中执行昂贵的计算，因此 Transformer 模型在可以覆盖的上下文窗口中受到很大限制。因此，可能仅可能将 Transformer 模型应用于有限的文本大小或生成简短的语句或音乐。GoogleAI 最近发布了一种有效的 Transformer 模型变体，称为Reformer[4]。该方法的主要焦点是能够处理更高的上下文窗口，同时减少计算需求并提高内存效率。重整器使用局部敏感哈希（LSH）将相似的向量分组在一起，并从其中创建片段，从而实现并行处理。然后将注意力转移到这些较小的部分和相应的相邻部分上，这就是减少计算负荷的原因。使用可逆层可实现存储效率，可逆层允许在通过反向传播进行训练时按需重新计算每层的输入信息。这是一种简单的技术，避免了需要在内存中存储激活的模型。查看此Colab notebook[5]，以了解如何将 Reformer 模型应用于图像生成任务。


\\
![](https://cdn-images-1.medium.com/max/800/0*Q6FHJ5bqZRCrBAp9.png)

\\
**1.4 用于文本分类的无监督域自适应**

\\
这项工作，Self-Attention with Relative Position Representations[6]，提出了将距离度量结合到附加损失函数中的方法，以训练模型并改善无监督域自适应。该模型被扩展为 DistanceNet Bandit 模型，该模型优化了“转移到低资源目标域”的结果。用这种方法解决的关键问题是如何处理来自不同域的数据之间的差异，特别是因为它涉及 NLP 任务（例如情感分析）。

\\
**1.5 改进的上下文表示**


\\
ELECTRA[7]提出了一种称为 token-detection 的样本效率更高的预训练任务，用于训练比掩盖的语言建模预训练方法（例如 BERT）更有效的语言模型。该模型 ELECTRA，在相同的数据和模型大小下，其上下文表示优于 BERT 和 XLNET。该方法特别适用于低计算方案， 这对建立更小和更便宜的语言模型又迈进了一步。

\\
**1.5 模型可解释性**

\\
Distill 最近出版的标题为“Visualizing the Impact of Feature Attribution Baselines[8]”的文章讨论了Integrated Gradients[9]，该梯度用于通过识别哪些特征与预测某个数据点相关来解释各种问题中的神经网络。问题在于正确定义和保留缺失概念，这是积分梯度的基线输入所要达到的目的。在模型可解释性的背景下，这里的挑战在于，该方法必须确保模型不会突出显示缺失的特征，而同时又避免给基线输入以零重要性，而这很容易发生。作者建议定量评估一些先前使用和建议的基线选择的不同效果，以更好地保留缺失概念。


## **2、Creativity and Society 🎨**

**2.1 情感不匹配**

\\
这项纵向研究，Emotions Extracted from Text vs. True Emotions[10]，发现通过使用基于文本的算法提取的情绪通常与自我报告的情绪不同。

\\
**2.2 多巴胺的理解和蛋白质折叠**

\\
DeepMind 最近在 Nature 杂志上发表了两篇有趣的论文。第一篇论文，Dopamine-and-temporal-difference-learning[11]，旨在通过强化学习更好地了解大脑中的多巴胺如何发挥作用。第二篇论文，AlphaFold-Using-AI-for-scientific-discovery[12]，与蛋白质折叠[13]更相关，并试图更好地理解它，以便能够潜在地发现多种疾病的治疗方法。这些都是很好的例子，说明了如何将 AI 系统潜在地应用于现实世界中的应用程序以帮助社会。

\\
![](https://cdn-images-1.medium.com/max/800/1*0mfEtacqGLSrmaUlNjJa0g.png)

\\
**2.3 有关 ML 的访谈**

\\
在接受 Wired 采访时，Refik Anadol 讨论了机器学习算法创造精美艺术[14]的潜力。这是如何将 ML 用于创造力的一个很好的例子。

\\
人工智能可能会产生重大影响的行业之一是教育。在The Future of Everything[15]的新剧集中，Russ Altman 和 Emma Brunskill 对计算机辅助学习进行了深入讨论。


# 3、Tools and Datasets ⚙️

**3.1 生产环境中的 PyTorch 模型**

\\
Cortex 是一种工具，可用于自动化基础架构并将 PyTorch 模型作为 API 部署在 AWS 中。点击这篇博文Using PyTorch Models in Production with Cortex[16]详细了解其操作方式。

\\
**3.2 可视化文本生成序列**

\\
Facebook AI 发布了VizSeq[17]，该工具可帮助以可视化方式评估 BLUE 和 METEOR 等指标下的文本生成序列。该工具的主要目标是通过利用可视化并使其对研究人员更具可扩展性和生产力，提供对文本数据集的更直观的分析。可以阅读原论文[18]获取更多信息。

\\
![](https://cdn-images-1.medium.com/max/800/1*Ff7BTxmEjUXHtYu9JkfClg.jpeg)

\\
**3.3 效果最优的在线语音识别**

\\
FacebookAI 开源wav2letter@anywhere[19]，这是一个推理框架，该推理框架基于基于 Transformer 的声学模型，用于最新的在线语音识别。重大改进涉及模型的大小，并减少了音频和转录之间的延迟，这对于实现更快的实时推理都很重要。

\\
![](https://cdn-images-1.medium.com/max/800/1*4_2Obuu8u8l2Vtp8UMHe7Q.gif)


## **4、Ethics in AI 🚨**

**4.1 AI implications**

\\
为了防止 AI 系统对公众的滥用和不道德行为，欧盟正在考虑五年内禁止公众使用面部识别技术，点此查看全文[20]。

\\
**4.2 现代自然语言处理的环境成本**

\\
也许大多数时候都被忽略了，Energy and Policy Considerations for Deep Learning in NLP 一文[21]讨论了 NLP 中现代深度学习方法的能量和政策考虑。众所周知，当前的模型依赖数十亿个参数，进而依赖大量的计算资源，从而消耗大量能源。作者希望对训练这些现代 NLP 模型所涉及的环境成本传播更多的认识。

\\
Zachary Lipton[22]在多伦多大学的演讲中讨论了公平性，可解释性和解决主义的危险，演讲主题围绕 ML 公平方法和含义。


# 5、Articles and Blog posts ✍️

**5.1 开源 ML**

\\
Hugging Face 的科学负责人 Thomas Wolf 为计划开源 ML 代码&研究[23]的人员提供了出色的建议。

\\
**5.2 计算机视觉的自监督学习**

\\
Jeremy Howard 在这篇出色的博客文章中，Self-supervised learning and computer vision[24]，简要介绍了在计算机视觉环境下进行自监督学习的概念。这些简短的摘要，有助于为你提供可靠的介绍，万一你有兴趣将这一领域的技术应用于自己的问题呢。

\\
**5.3 用于搜索的 TinyBERT**

\\
我们已经看到许多 BERT 模型的变体（例如 DistilBERT）的成功，这些变体使用某种形式的知识蒸馏来显着减小模型大小并提高速度。一些人使用了 BERT 的变体 TinyBERT，并将其应用于基于关键字的搜索解决方案。此项目的灵感来自于该搜索解决方案，该解决方案用于理解 Google 提出的搜索。该体系结构的很大一部分是，它可以在标准 CPU 上工作，并且可以用于改善和理解搜索结果。

\\
**5.4 主动转移学习**

\\
Rober Monarch 这篇有关主动转移学习[25]的博客文章十分有趣，这是他即将出版的《Human-in-the-loop Machine Learning[26]》一书的一部分。他目前正在写很棒的博客文章，介绍结合人与机器智能解决问题的方法，他还提供了所讨论方法的随附 PyTorch 实现。


\\
**5.5 Revealing the Dark Secrets of BERT**

\\
Anna Roger 撰写了一篇有趣而有趣的博客文章， the Dark Secrets of BERT[27]，其中讨论了经过微调的 BERT 的实际情况，以及所宣称的优势是否用于处理诸如情感分析，文本含义和自然语言推断等下游任务。分析的结果表明，BERT 的参数过高，并且该框架的自注意力组件由于它与被编码并用于推理的语言信息有关，所识别出的好处不一定特别如其所主张的。

# 6、Education 🎓

**6.1 Neural Nets for NLP**

\\
CMU 的 NLP 教授 Graham Neubig 已经发布了本学期提供的“ NLP 神经网络”课程[28]的视频。对于那些对现代 NLP 方法学习感兴趣的人，我强烈推荐该播放列表。

\\
**6.2 深度学习数学**

\\
是否想深入研究深度学习方法背后的数学[29]？这个视频讲座系列，已经拥有众多演讲者。

\\
**6.3 Python 课程和教程**

\\
Python 不仅在 IT 行业而且在数据科学领域也已成为最受欢迎的编程语言之一。为了向全世界的学习者提供 Python 的实践知识，Google 发布了“Google IT Automation with Python Professional Certificate[30]”课程。尽管该课程与 ML 或 AI 并没有直接关系，但这绝对是精通 Python 语言的不错的基础课程，并且提供奖学金。


\\
这是另一个很有前景的视频系列，称为“Deep Learning (for Audio) with Python[31]”，重点是利用 Tensorflow 和 Python 通过利用深度学习来构建与音频/音乐相关的应用程序。

\\
![](https://cdn-images-1.medium.com/max/800/1*N5d8-1La8khZ6-XwHL68sg.png)

\\
**6.4 Deep Learning State of the Art**

\\
观看 Lex Fridman 关于深度学习的最新研究和发展[32]的视频讲座。他谈到了诸如感知器，神经网络，反向传播，CNN，深度学习，ImageNet，GAN，AlphaGo 和最新的 Transformers 等主题的重大突破，本讲座是 MIT 深度学习系列的一部分。

\\
**6.5 在线学习和研究**

\\
有许多很棒的在线计划可以在研究和学习中进行协作。我个人最喜欢的是MLT 的数学阅读课程[33]，这项由 Nightai 发起的新的分布式 AI 研究协作计划。最近，有许多这样的在线研究小组，它们是沉浸于 ML 世界的好方法。

\\
**6.6 The landscape of Reinforcement Learning**

\\
在网络研讨会上向 Katja Hofmann 博士学习强化学习[34]的关键概念、方法，以及学习方向。

# 7、Notable Mentions ⭐️

查看适用于 CIFAR-10 的ResNet-18 的 PyTorch 实现[35]，该实现可实现约 94％的准确度。

\\
PyTorch 1.4[36]发布了！在此处查看发行说明。

\\
Elona Shatri 撰写了一篇出色的摘要，说明了她打算如何使用深度学习进行光学音乐识别[37]。

\\
看博客文章的标题就知道啦：“贝叶斯深度学习案例[38]”。

\\
Chris Said 分享了他在优化 A/B 测试样本量[39]方面的经验，这是实用数据科学的重要组成部分。主题包括大样本量的成本和收益以及从业人员的最佳实践。

\\
Neural Data Server (NDS)[40] 是用于获取转移学习数据的专用搜索引擎， 在此处阅读有关方法和服务[41]的信息。

\\
**本文参考资料**

\\
[1] **Can You Trust Your Model's Uncertainty?:** https://arxiv.org/abs/1906.02530

\\
[2] **官方博客:** https://ai.googleblog.com/2020/01/can-you-trust-your-models-uncertainty.html

\\
[3] **Systematic Generalization: What Is Required and Can It Be Learned?:** https://www.semanticscholar.org/paper/Systematic-Generalization:-What-Is-Required-and-Can-Bahdanau-Murty/6c7494a47cc5421a7b636c244e13586dc2dab007

\\
[4] **Reformer:** https://ai.googleblog.com/2020/01/reformer-efficient-transformer.html

\\
[5] **Colab notebook:** https://colab.research.google.com/github/google/trax/blob/master/trax/models/reformer/image_generation.ipynb

\\
[6] **Self-Attention with Relative Position Representations:** https://arxiv.org/abs/2001.04362

\\
[7] **ELECTRA:** https://openreview.net/forum?id=r1xMH1BtvB

\\
[8] **Visualizing the Impact of Feature Attribution Baselines:** https://distill.pub/2020/attribution-baselines/

\\
[9] **Integrated Gradients:** https://medium.com/@kartikeyabhardwaj98/integrated-gradients-for-deep-neural-networks-c114e3968eae

\\
[10] **Emotions Extracted from Text vs. True Emotions:** https://ieeexplore.ieee.org/abstract/document/8952437

\\
[11] **Dopamine-and-temporal-difference-learning:** https://deepmind.com/blog/article/Dopamine-and-temporal-difference-learning-A-fruitful-relationship-between-neuroscience-and-AI

\\
[12] **AlphaFold-Using-AI-for-scientific-discovery:** https://deepmind.com/blog/article/AlphaFold-Using-AI-for-scientific-discovery[13]**蛋白质折叠:** https://en.wikipedia.org/wiki/Protein_folding

\\
[14] **机器学习算法创造精美艺术:** https://www.youtube.com/watch?v=I-EIVlHvHRM&feature=youtu.be

\\
[15] **The Future of Everything:** https://engineering.stanford.edu/magazine/article/emma-brunskill-amped-education-ai?sf115875862=1

\\
[16] **Using PyTorch Models in Production with Cortex:** https://medium.com/pytorch/how-to-build-production-software-with-pytorch-9a8725382f2a

\\
[17] **VizSeq:** https://ai.facebook.com/blog/vizseq-a-visual-analysis-toolkit-for-accelerating-text-generation-research/

\\
[18] **论文:** https://www.aclweb.org/anthology/D19-3043.pdf

\\
[19] **wav2letter@anywhere:** https://ai.facebook.com/blog/online-speech-recognition-with-wav2letteranywhere/

\\
[20] **查看全文:** https://www.reuters.com/article/us-eu-ai/eu-mulls-five-year-ban-on-facial-recognition-tech-in-public-areas-idUSKBN1ZF2QL

\\
[21] **Energy and Policy Considerations for Deep Learning in NLP一文:** https://arxiv.org/abs/1906.02243

\\
[22] **Zachary Lipton:** https://c4ejournal.net/2020/01/16/zack-lipton-fairness-interpretability-and-the-dangers-of-solutionism-ethics-of-ai-in-context2020-c4ej-2/

\\
[23] **开源ML代码&研究:** https://twitter.com/Thom_Wolf/status/1216990543533821952?s=20

\\
[24] **Self-supervised learning and computer vision:** https://www.fast.ai/2020/01/13/self_supervised/

\\
[25] **主动转移学习:** https://medium.com/pytorch/https-medium-com-robert-munro-active-learning-with-pytorch-2f3ee8ebec

\\
[26] **Human-in-the-loop Machine Learning:** https://www.manning.com/books/human-in-the-loop-machine-learning

\\
[27] **the Dark Secrets of BERT:** https://text-machine-lab.github.io/blog/2020/bert-secrets/

\\
[28] **“ NLP神经网络”课程:** https://www.youtube.com/playlist?list=PL8PYTP1V4I8CJ7nMxMC8aXv8WqKYwj-aJ

\\
[29] **深度学习方法背后的数学:** https://www.youtube.com/playlist?list=PLWQvhvMdDChzsThHFe4lYAff3pu2m0v2H

\\
[30] **Google IT Automation with Python Professional Certificate:** https://www.coursera.org/professional-certificates/google-it-automation

\\
[31] **Deep Learning (for Audio) with Python:** https://www.youtube.com/watch?v=fMqL5vckiU0&list=PL-wATfeyAMNrtbkCNsLcpoAyBBRJZVlnf

\\
[32] **深度学习的最新研究和发展:** https://www.youtube.com/watch?v=0VH1Lim8gL8

\\
[33] **MLT的数学阅读课程:** https://twitter.com/**「MLT」**

\\
[34] **强化学习:** https://note.microsoft.com/MSR-Webinar-RL-Algorithm-to-Adoption-Registration-Live.html?wt.mc_id=twitter_MSR-WBNR_post_v3

\\
[35] **ResNet-18的PyTorch实现:** https://gist.github.com/y0ast/d91d09565462125a1eb75acc65da1469

\\
[36] **PyTorch 1.4:** https://github.com/pytorch/pytorch/releases/tag/v1.4.0

\\
[37] **使用深度学习进行光学音乐识别:** https://medium.com/@e.shatri1/what-is-optical-music-recognition-6515d8a53e01

\\
[38] **贝叶斯深度学习案例:** https://cims.nyu.edu/~andrewgw/caseforbdl/

\\
[39] **优化A/B测试样本量:** https://chris-said.io/2020/01/10/optimizing-sample-sizes-in-ab-testing-part-I/

\\
[40] **Neural Data Server (NDS):** https://arxiv.org/abs/2001.02799[41]**服务:** http://aidemos.cs.toronto.edu/nds/
