---
layout: post
title: "NLP 简报（Issue#7）: NLP Paper Summaries, Learning to Simulate, Transformers Notebooks, Med7, Measuring Compositional Generalization, Neural Tangents,…"
author: KaiyuanGao
excerpt: "在本期中，我们涵盖的主题包括了从如何改进测量成分泛化到计算机视觉PyTorch库到最新的物理模拟器等."
modified:
comments: true
tags: [nlp_newsletter]
image:
  thumb: nlp_newsletter_7.png
---

![](https://cdn-images-1.medium.com/max/1200/1*9gNslKwKiRaffDt2RSOgoQ.png)

\\
欢迎来到NLP简报第七期。
Welcome to the 7th issue of the NLP Newsletter.希望您今天过得愉快，并希望您和您的亲人在这个困难的日子里平安无事。我们决定发布此新闻通讯，以使我们的读者感到高兴，因此请在有空的时候阅读。现在，让我们继续关注最重要的事情-我们的家人和朋友。 ❤️ 💛 💚

\\
***一些关于NLP简报以及dair.ai的更新***
之前每一期NLP简报的法语和中文翻译都已经完成，可以在 [这里](https://github.com/dair-ai/nlp_newsletter)查看. [在此](https://github.com/dair-ai/dair-ai.github.io/issues/11)了解如何为NLP新闻通讯的前期和即将发行的翻译做出贡献。

\\
我们最近建立了两个Github库： [NLP paper summaries](https://github.com/dair-ai/nlp_paper_summaries) 以及[PyTorch notebooks](https://github.com/dair-ai/pytorch_notebooks) 。


# 1、Research and Publications 📙

#### 1.1 Measuring Compositional Generalization

\\
在机器学习的背景下，合成泛化（compositional generalization）是指机器学习从一组训练示例学习上下文表示。 迄今为止，尚不清楚如何正确地测量神经网络中的compositionality。Google AI研究者在 ICLR 2020 上的论文《[Measuring Compositonal Generalization: A Comprehensive Method on Realistic Data](https://ai.googleblog.com/2020/03/measuring-compositional-generalization.html)》，提出了使用问题解答和语义解析等任务进行compositional generalization的最大基准之一。 下图显示了该种新模型，使用原子（prodece，direct等）来产生新化合物（即原子的组合）的示例。 这项工作的想法是产生一个训练测试拆分，其中包含共享相似原子（生成示例的构造块）但具有不同化合物分布（原子组成）的示例。 作者声称这是测试compositional generalization的一种更可靠的方法。

\\
![](https://cdn-images-1.medium.com/max/800/0*lXmUWOY8HJL7YVn1.gif)

*Credit: Google AI Blog*


#### 1.2 微调预训练语言模

\\
研究人员进行了一系列全面的微调试验，以更好地了解权重初始化和早停对语言模型的效果，发表在论文《[Fine-Tuning Pretrained Language Models: Weight Initializations, Data Orders, and Early Stopping](https://arxiv.org/abs/2002.06305)》中。 通过涉及对BERT进行数百次微调的各种实验，发现不同的随机种子会产生截然不同的结果。特别是，该研究报告称，一些权重初始化在一组任务中确实表现良好。所有实验数据和试验均已公开发布，供有兴趣进一步了解微调过程中不同动态的其他研究人员使用。


#### 1.3 Zoom In: An Introduction to Circuits

\\
OpenAI研究人员发表了一篇文章，[Zoom In: An Introduction to Circuits](https://distill.pub/2020/circuits/zoom-in/)，讨论了神经网络的可解释性状态，并提出了一种解释神经网络的新方法的建议。受细胞生物学的启发，作者通过检查神经网络的权重深入了解了视觉模型以及他们学到了什么。本质上，该研究提出了他们认为可以为更好地解释神经网络铺平道路的一些主张以及证据。

\\
![](https://cdn-images-1.medium.com/max/800/1*i0c-qpiire6dD4IqJVKlYg.png)


#### 1.4 NLP Research Highlights — Issue #1

\\
在dair.ai的新系列[NLP Research Highlights](https://medium.com/dair-ai/nlp-newsletter-bertology-primer-fastpages-t5-data-science-education-pytorch-notebooks-slow-8ae5d499e040)中，详细介绍了当前有趣且重要的NLP研究。通过对这些工作的总性，这将成为跟踪NLP进展的一种方式。在第一季度中，主题涉及从改进语言模型到改进对话代理到最新的语音识别系统。 这些摘要也将保留在[nlp_paper_summaries](https://github.com/dair-ai/nlp_paper_summaries)中。


#### 1.5用图网络模拟复杂物理

\\
在过去的几个月中，由于图神经网络（GNN）不仅在NLP中有效，而且在基因组学和材料等其他领域也非常有效，因此我们一直在关注它们。在最近的一篇论文中，《[Learning to Simulate Complex Physics with Graph Networks](https://arxiv.org/abs/2002.09405)》，研究人员提出了一种基于图网络的通用框架，该框架能够学习流体和可变形材料等不同领域的模拟。 作者声称他们在不同领域都实现了最先进的性能，他们的通用方法可能是迄今为止学得最好的物理模拟器。 实验包括对材料的模拟，例如在水上滑行以及其他与刚性障碍物的相互作用。 他们还测试了关于分发任务的预训练模型，并找到了可喜的结果，表明该框架已推广到更大的领域。

\\
![](https://cdn-images-1.medium.com/max/800/1*48EolUDJoHpYRCTZxgn_qg.png)

[*(Sanchez-Gonzalez et al., 2020)*](https://arxiv.org/pdf/2002.09405.pdf)


#### 1.6 特定语言BERT模型

\\
Hugging Face Transformer库中现在提供阿拉伯语BERT（AraBERT）。 你可以访问[AraBERT模型](https://huggingface.co/aubmindlab/bert-base-arabert)以及对应的[AraBERT论文(https://arxiv.org/abs/2003.00104);

最近还发布了[日语BERT](https://github.com/akirakubo/bert-japanese-aozora)以及波兰语BERT[Polbert](https://github.com/kldarek/polbert)。

# 2、Creativity, Ethics, and Society 🌎

#### 2.1 COVID-19相关的蛋白质结构的计算预测

\\
DeepMind公开与COVID-19相关病毒相关的蛋白质的计算预测结构，[computational-predictions-of-protein-structures-associated-with-COVID-19](https://deepmind.com/research/open-source/computational-predictions-of-protein-structures-associated-with-COVID-19)。这些预测是直接从AlphaFold系统获得的，但尚未经过实验验证。该开源的初衷是鼓励为更好地了解该病毒及其功能做出贡献。


#### 2.2 Court cases that sound like the weirdest fights

\\
Janelle Shane分享了一个有趣实验的结果，[court-cases-that-sound-like-the-weirdest-fights](https://aiweirdness.com/post/612669075940900864/court-cases-that-sound-like-the-weirdest-fights)，其中对GPT-2模型进行了微调以生成针对无生命物体的案例。该模型喂入了一系列政府扣押违禁品或危险品的案例，并生成了如下图所示的案例。

\\
![](https://cdn-images-1.medium.com/max/800/0*E5mHmkm1h4VQJ2Ni.png)

[*Source*](https://aiweirdness.com/post/612669075940900864/court-cases-that-sound-like-the-weirdest-fights)

#### 2.3 以人为中心的ML框架设计

\\
Google AI公布了对使用TensorFlow.js的645人的大规模调查结果，[toward-human-centered-design-for-ml](https://ai.googleblog.com/2020/03/toward-human-centered-design-for-ml.html)。 他们旨在从非ML软件开发人员那里了解最重要的功能是什么，以及他们在使用当前ML框架时的总体经验。研究发现包括“缺乏对ML的概念性理解”阻碍了ML框架针对此特定用户集的使用。该研究的参与者还报告了关于如何将ML模型应用于不同问题的需求


#### 2.4 在浏览器中进行面部和手部跟踪

\\
这篇很棒的TensorFlow文章，[Toward Human-Centered Design for ML Frameworks](https://blog.tensorflow.org/2020/03/face-and-hand-tracking-in-browser-with-mediapipe-and-tensorflowjs.html?linkId=83996111)，提供了如何使用TensorFlow.js和MediaPipe在浏览器上启用实时面部和手部跟踪的演练。


\\
![](https://cdn-images-1.medium.com/max/800/0*XsRsB-tSOZo9yWOc.gif)

*Credit: TensorFlow Blog*


# Tools and Datasets ⚙️

#### 3.1 NLP Paper Summaries

\\
我们最近创建了一个[nlp_paper_summaries库](https://github.com/dair-ai/nlp_paper_summaries)，其中包含经过精心挑选的NLP论文摘要列表，这些摘要是过去几年中一些最有趣和最重要的NLP论文。着重于精选重要论文的论文摘要和博客文章，以帮助提高NLP主题和研究的可及性。


#### 3.2 PyTorch的计算机视觉库

\\
[Kornia](https://github.com/kornia/kornia) 是建立在PyTorch之上的开源库，它使研究人员可以使用一组运算符来使用PyTorch执行不同的计算机视觉。某些功能包括图像转换，深度估计和低级图像处理等。它在很大程度上受到OpenCV的启发，但不同之处在于，它旨在用于研究，而不是构建可投入生产的应用程序。

\\
![](https://cdn-images-1.medium.com/max/800/0*gN_-llcA4_3lIHYE.gif)


#### 3.3 DIET简介

\\
[DIET（Dual Intent and Entity Transformer）](https://blog.rasa.com/introducing-dual-intent-and-entity-transformer-diet-state-of-the-art-performance-on-a-lightweight-architecture/)是Rasa提出的自然语言理解（NLU）多任务体系结构。 该框架着重于多任务训练，以改善意图分类和实体识别方面的结果。 DIET的其他好处包括能够使用任何当前的预训练嵌入，例如BERT和GloVe。重点是要提供一个模型，这些模型可以提高这些任务的当前最新性能，并且训练速度更快（据报道，速度提高了6倍）。 该模型在[Rasa开源python库](https://rasa.com/docs/rasa/1.8.0/nlu/components/#dietclassifier)中可用.

\\
![](https://cdn-images-1.medium.com/max/800/0*R_8FOU-CVZabv7hJ.jpg)

[*DIET framework*](https://blog.rasa.com/introducing-dual-intent-and-entity-transformer-diet-state-of-the-art-performance-on-a-lightweight-architecture/?utm_source=twitter)


#### 3.4 迷失在众多BERT模型中？
[BERT Lang Street](https://bertlang.unibocconi.it/)是一个简洁的网站，它能够搜索30种基于BERT的模型，其中包含18种语言和28个任务，共177个条目。 例如，如果你想使用BERT模型找出最新的情感分类结果，则可以在搜索栏中搜索“情感”（如下面的图片所示）。


\\
![](https://cdn-images-1.medium.com/max/800/1*UuVno2eOAzYb_wlSSfukPA.png)


#### 3.5 Med7

\\
Andrey Kormilitzin发布了[Med7](https://github.com/kormilitzin/med7) ，这是一种用于在电子健康记录上执行临床NLP（特别是命名实体识别（NER）任务）的模型。该模型最多可以识别七个类别，并且可以与spaCy库一起使用。


\\
![](https://cdn-images-1.medium.com/max/800/1*yOMqhvTwYnxB4LYXv2Mgjg.png)


#### 3.6 量子机器学习开源库

\\
[TensorFlow Quantum](https://ai.googleblog.com/2020/03/announcing-tensorflow-quantum-open.html)是一个开放源代码库，提供了用于快速进行量子ML研究原型的工具箱，该工具箱应用ML模型来解决从医学到材料的各种问题。



#### 3.7 快速简便的无限宽网络

\\
[Neural Tangents](https://github.com/google/neural-tangents)是一个开放源代码库，允许研究人员使用JAX建立和训练无限宽模型和有限神经网络。可以阅读相应地博客获取更多信息，[fast-and-easy-infinitely-wide-networks](https://ai.googleblog.com/2020/03/fast-and-easy-infinitely-wide-networks.html)。


\\
![](https://cdn-images-1.medium.com/max/800/1*CojgKJwB_n_7-j0DJZ0y7g.png)

# Articles and Blog posts ✍️

#### 4.1 从 PyTorch 到JAX

\\
Sabrina J. Mielke发表了一篇文章，[From PyTorch to JAX: towards neural net frameworks that purify stateful code](https://sjmielke.com/jax-purify.htm)，其中提供了有关如何使用JAX构建和训练神经网络的演练。 本文着重于在构建神经网络时比较PyTorch和JAX的内部工作原理，这有助于更好地理解JAX的一些优点和区别。

\\
![](https://cdn-images-1.medium.com/max/800/0*Nrw4UnmnIZ__elHu.png)

[*Source*](https://sjmielke.com/jax-purify.htm) **


#### 4.2 Why do we still use 18-year old BLEU?***

\\
在博客[ Why do we still use 18-year old BLEU?](https://ehudreiter.com/2020/03/02/why-use-18-year-old-bleu/)中，Ehud Reiter谈到了为什么我们仍然使用BLUE等旧的评估技术进行评估诸如机器翻译之类的任务的NLP模型。作为该领域的研究人员，他还表达了对对较新任务进行评估的技术的含义。


#### 4.3 BART简介

\\
[BART](https://arxiv.org/abs/1910.13461)是Facebook提出的一种新模型，其中涉及一种用于对seq2seq模型进行预训练的降噪自动编码器，该模型可以改善下游文本生成任务（如抽象摘要）的性能。 Sam Shleifer提供了[BART的摘要简介](https://sshleifer.github.io/blog_v2/jupyter/2020/03/12/bart.html)，以及他如何将其集成到Hugging Face Transformers代码库中。



#### 4.4 Transformer长程上下文综述

\\
Madison May最近写了一篇有趣的综述，[A Survey of Long-Term Context in Transformers](https://www.pragmatic.ml/a-survey-of-methods-for-incorporating-long-term-context/)，描述了改进基于Transformer的方法，其中包括Sparse Transformers, Adaptive Span Transformers, Transformer-XL, compressive Transformers, Reformer以及routing transformer。


#### 4.5 如何在自动文本编写中控制样式和内容

\\
尽管自动文本书写在过去的一年中展现了令人印象深刻的表现，但是控制诸如机器书写文本的结构或内容之类的属性仍然具有挑战性。 在最近的博客文章，[“Mind your language, GPT-2”: how to control style and content in automatic text writing](https://creatext.ai/blog-posts/controllable-text-generation)中，Manuel Tonneau从Hugging Face的GPT-2讨论了可控文本生成领域的最新进展和观点。 该模型在arXiv上与Google的T5进行了微调，并提到了Salesforce的CTRL和Uber AI的PPLM。


# Education 🎓

#### 5.1 Python中NLP的未来发展

\\
在我们以前的NLP简报中，我们介绍了[THiNC](https://thinc.ai/)，这是一个功能深层学习库，致力于与其他现有库的兼容性。 Ines Montani在PyCon哥伦比亚的演讲使用的PPT[The Future of NLP in Python](https://speakerdeck.com/inesmontani/the-future-of-nlp-in-python-keynote-pycon-colombia-2020?slide=9)引入了更多的库。


#### 5.2 Transformers Notebooks

\\
HuggingFace发布了一组[Colab notebooks](https://github.com/huggingface/transformers/tree/master/notebooks)，可帮助他们开始使用流行的Transformers库。 一些notebook包括使用令牌化，设置NLP管道以及在自定义数据上训练语言模型。


\\
![](https://cdn-images-1.medium.com/max/800/1*0AYHYUsHbaqV2vqN2zCzLQ.png)


#### 5.3 TensorFlow 2.0免费课程

\\
在TensorFlow 2.0上查看此[〜7小时免费课程](https://www.freecodecamp.org/news/massive-tensorflow-2-0-free-course/) ，其中包含从基本神经网络到NLP到强化学习的介绍。


#### 5.4 DeepMind播客

\\
DeepMind已为其播客发布了所有剧集，[DeepMind: The Podcast](https://www.youtube.com/playlist?list=PLqYmG7hTraZBiUr6_Qf8YTS2Oqy3OGZEj)，其中有科学家，研究人员和工程师讨论主题涵盖了AGI 到 神经科学 到 机器人技术。



#### 5.5 ML&DL课程

\\
[Berkeley的“深度无监督学习”课程](https://sites.google.com/view/berkeley-cs294-158-sp20/home)已经公开发布整个教学大纲，主要侧重于自我学习的理论方面 监督学习和生成模型。一些主题包括潜在变量模型，自回归模型，流模型和自我监督学习等等，已经有提供YouTube视频和幻灯片。


\\
我们还发现了有关机器学习，NLP和深度学习的高级在线课程的令人印象深刻的列表，[d_advanced_courses_update](https://www.reddit.com/r/MachineLearning/comments/fdw0ax/d_advanced_courses_update/) 。


\\
这是另一门名为[“机器学习入门”](https://compstat-lmu.github.io/lecture_i2ml/index.html)的课程，其中包括诸如监督回归，性能评估，随机森林，参数调整， 实用建议等。


# Noteworthy Mentions ⭐️

上一期的NLP简报(Issue #6) 可以在[这里](https://medium.com/dair-ai/nlp-newsletter-bertology-primer-fastpages-t5-data-science-education-pytorch-notebooks-slow-8ae5d499e040)查看。

\\
Connon Shorten发表了解释[ELECTRA模型的视频](https://www.youtube.com/watch?v=QWu7j1nb_jI&feature=emb_logo)，该模型提出了一种称为 `replaced token detection`的技术，可以更有效地对Transformers进行预训练。 如果您有兴趣，我们也在[此处](https://medium.com/dair-ai/nlp-research-highlights-cd522b21b01a)写了该模型的简短摘要。


\\
Rachael Tatman正在研究一个名为[面向开发人员的NLP](https://www.youtube.com/watch?v=-G36q8_cYsc&feature=emb_logo) 的新系列，其目的是在何时使用NLP的方法进行更深入的讨论,使用它们并解释你可能遇到的常见问题。

\\
DeepMind在YouTube上发布了[AlphaGo-电影](https://youtu.be/WXuK6gekU1Y)，以庆祝AlphaGo在Go游戏中击败Lee Sedol四周年。


\\
OpenMined为研究工程师和研究科学家[开放职位](https://blog.openmined.org/introducing-openmined-research/)，这是参与保护隐私的AI的好机会。

----------
如果您希望在下一期NLP新闻通讯中共享任何数据集，项目，博客文章，教程或论文，请随时通过ellfae@gmail.com或[**DM on Twitter**](https://twitter.com/omarsar0)。


\\
[*Subscribe*](https://dair.ai/newsletter/)*🔖至NLP新闻通讯，以在收件箱中接收以后的新闻。*
