---
layout: post
title: "NLP Newsletter #6: BERTology Primer, fastpages, T5, Data Science Education, PyTorch Notebooks, Slow Science in ML"
author: billy_rick
modified:
comments: true
excerpt: "This issue covers topics that range from extending the Transformer model to slowing publication in ML to a series of ML and NLP books and project releases."
tags: [nlp_newsletter]
image:
  thumb: nlp_newsletter_6.png
---



![](https://cdn-images-1.medium.com/max/1200/1*vWICxAehSy3xOnqGIXtpoQ.png)

\\
Welcome to the sixth issue of the NLP Newsletter. Thanks for all the support and for taking the time to read through the latest in ML and NLP. This issue covers topics that range from extending the Transformer model to slowing publication in ML to a series of ML and NLP book and project launches.

\\
***A few updates about the NLP Newsletter and dair.ai***

\\
We have been translating the newsletter to other languages such as Brazilian Portuguese, Chinese, Arabic, Spanish, among others. Thanks to those folks that have helped with the translations 🤗. You can also contribute [here](https://github.com/dair-ai/dair-ai.github.io/issues/11).

\\
A month ago, we officially launched our new [website](https://dair.ai/). You can look at our [GitHub organization](https://github.com/dair-ai) for more information about dair.ai and projects. If you are interested in seeing how others are already contributing to dair.ai or are interested in contributing to democratizing artificial intelligence research, education, and technologies, check our [issues](https://github.com/dair-ai/dair-ai.github.io/issues) section.

\\
[*Subscribe*](https://dair.ai/newsletter/) *🔖 to the NLP Newsletter to receive future issues in your inbox.*


# Publications 📙

***A Primer in BERTology: What we know about how BERT works***

\\
Transformer-based models have shown to be effective at approaching different types of NLP tasks that range from *sequence labeling* to *question answering*. One of those models called BERT [(Devlin et al. 2019)](https://arxiv.org/abs/1810.04805) is widely used but, like other models that employ deep neural networks, we know very little about their inner workings. A new [paper](https://arxiv.org/abs/2002.12327) titled “**A Primer in BERTology: What we know about how BERT works**” aims to answer some of the questions about why BERT performs well on so many NLP tasks. Some of the topics addressed in the paper include the type of knowledge learned by BERT and where it is represented, and how that knowledge is learned and other methods researchers are using to improve it.

\\
***Exploring the Limits of Transfer Learning with a Unified Text-to-Text Transformer***

\\
Google AI recently published a [method](https://arxiv.org/abs/1910.10683) that brings together all the lessons learned and improvements from NLP transfer learning models into one unified framework called Text-to-Text Transfer Transformer (T5). This work proposes that most NLP tasks can be formulated in a text-to-text format, suggesting that both the inputs and outputs are texts. The authors claim that this “*framework provides a consistent training objective both for pre-training and fine-tuning*”. T5 is essentially an encoder-decoder Transformer that applies various improvements in particular to the attention components of the model. The model was pre-trained on a newly released dataset called [Colossal Clean Crawled Corpus](https://www.tensorflow.org/datasets/catalog/c4) and achieved SOTA results on NLP tasks such as summarization, question answering, and text classification.

\\
![](https://cdn-images-1.medium.com/max/800/1*T9MXxcDOd2fX6xblbu7VdQ.png)


[*(Raffel et al. 2020)*](https://arxiv.org/abs/1910.10683)

\\
***12-in-1: Multi-Task Vision and Language Representation Learning***

\\
Current research uses independent tasks and datasets to perform vision-and-language research even when the “*visually-grounded language understanding skill*s” required to perform these tasks overlap. A new [paper](https://arxiv.org/abs/1912.02315) (to be presented at CVPR) proposes a large-scale multi-task approach to better model and jointly train vision-and-language tasks to generate a more generic vision-and-language model. The model reduces the parameter size and performs well on tasks like caption-based image retrieval and visual question answering.

\\
![](https://cdn-images-1.medium.com/max/800/1*yyvN4bK0K2iykyJ2-QVBjw.png)


[*(Lu et al. 2020)*](https://arxiv.org/abs/1912.02315)

\\
***BERT Can See Out of the Box: On the Cross-modal Transferability of Text Representations***

\\
reciTAL researchers and collaborators published a paper that aims to answer the question of whether a BERT model can produce representations that generalize to other modalities beyond text such as vision. They propose a model called BERT-gen that leverages mono or multi-modal representations and achieve improved results on visual question generation datasets.

\\
![](https://cdn-images-1.medium.com/max/800/1*2NgR7yBuVLDcEza9UT41dw.png)


[*(Scialom et al. 2020)*](https://arxiv.org/abs/2002.10832)


# Creativity and Society 🎨

***The Next Decade in AI: Four Steps Towards Robust Artificial Intelligence***

\\
Gary Marcus recently published a [paper](https://arxiv.org/abs/2002.06177) where he explains a series of steps that, in his view, we should be taking to build more robust AI systems. Gary’s central idea in this paper is to focus on building hybrid and knowledge-driven systems guided by cognitive models as opposed to focusing on building larger systems that require more data and computation power.

\\
***10 Breakthrough Technologies 2020***

\\
MIT Technology Review published a list of the [10 breakthroughs](https://www.technologyreview.com/lists/technologies/2020/) they have identified that will make a difference in solving problems that could change the way we live and work. The list — in no particular order — includes unhackable internet, hyper-personalized medicine, digital money, anti-aging drugs, AI-discovered molecules, satellite mega-constellations, quantum supremacy, Tiny AI, differential privacy, and climate attribution.

\\
***Time to rethink the publication process in machine learning***

\\
Yoshua Bengio recently [wrote](https://yoshuabengio.org/2020/02/26/time-to-rethink-the-publication-process-in-machine-learning/) on his concerns about the fast-paced cycles of ML publications. The main concern is that due to the velocity of publishing, a lot of papers get published that contain errors and are just incremental, whereas spending more time and ensuring rigour, which is how it used to work many years ago, seems to be vanishing. On top of it all, students are the ones that have to deal with the negative consequences of this pressure and stress. To address the situation, Bengio talks about his actions to help in the process of slowing down research publications for the good of science.


# Tools and Datasets ⚙️

***PointerGenerator network implementation in AllenNLP***

\\
Pointer-Generator networks aim to augment sequence-to-sequence attentional models that are used to [improve](https://arxiv.org/abs/1704.04368) [*abstractive summarization*](https://arxiv.org/abs/1704.04368). If you wish to use this technique for abstractive summarization using AllenNLP, Kundan Krishna has developed a [library](https://github.com/kukrishna/pointer-generator-pytorch-allennlp) that allows you to run a pretrained model (provided) or train your own model.

\\
![](https://cdn-images-1.medium.com/max/800/1*Fa4G6BrnJm3NSDr3TDHhfw.jpeg)

\\
***Question answering for different languages***

\\
With the proliferation of Transformer models and their effectiveness for large-scale NLP tasks performed in other languages, there has been an impressive amount of effort to release different types of datasets in different languages. For instance, Sebastian Ruder [shared](https://twitter.com/seb_ruder/status/1231713840502657025?s=20) a list of datasets that can be used for question answering research in different languages: [DuReader](https://www.aclweb.org/anthology/W18-2605/), [KorQuAD](https://arxiv.org/abs/1909.07005), [SberQuAD](https://arxiv.org/abs/1912.09723), [FQuAD](https://arxiv.org/abs/2002.06071), [Arabic-SQuAD](https://arxiv.org/abs/1906.05394), [SQuAD-it](https://github.com/crux82/squad-it), and [Spanish SQuAD](https://arxiv.org/abs/1912.05200v2).

\\
***PyTorch Lightning***

\\
PyTorch Lightning is a [tool](https://towardsdatascience.com/from-pytorch-to-pytorch-lightning-a-gentle-introduction-b371b7caaf09) that allows you to abstract training that could require setting up GPU/TPU training and the use of 16-bit precision. Getting those things to work can become tedious but the great news is that PyTorch Lightning simplifies this process and allows you to train models on multi GPUs and TPUs without the need to change your current PyTorch code.

\\
***Graph Neural Networks in TF2***

\\
A Microsoft Research team releases a [library](https://github.com/microsoft/tf2-gnn) that provides access to implementations of many different graph neural network (GNN) architectures. This library is based on TensorFlow 2 and also provides data-wrangling modules that can directly be used in training/evaluation loops.

\\
***Pre-training SmallBERTa — A tiny model to train on a tiny dataset***

\\
Have you ever wanted to train your own language model from scratch but didn’t have enough resources to do so? If so, then Aditya Malte have you covered with this great [Colab notebook](https://gist.github.com/aditya-malte/2d4f896f471be9c38eb4d723a710768b#file-smallberta_pretraining-ipynb) that teaches you how to train an LM from scratch with a smaller dataset.


# Ethics in AI 🚨

***Why faces don’t always tell the truth about feelings***

\\
For some time now, many researchers and companies have attempted to build AI models that understand and can recognize emotions either in the textual or visual context. A new [article](https://www.nature.com/articles/d41586-020-00507-5) reopens the debate that AI techniques that aim to recognize emotion directly from face images are not doing it right. The main argument, raised by prominent psychologists in the space, is that there is no evidence of universal expressions that can be used for emotion detection from face images alone. It would take a model better understanding of personality traits, body movement, among other things to really get closer to more accurately detecting the emotions displayed by humans.

\\
***Differential Privacy and Federated Learning Explained***

\\
One of the ethical considerations when building AI systems is to ensure privacy. Currently, this can be achieved in two ways, either using differential privacy or federated learning. If you want to know more about these topics, Jordan Harrod provides us a great introduction in this [video](https://www.youtube.com/watch?v=MOcTGM_UteM) which also includes a hands-on practice session with the use of a Colab notebook.


# Articles and Blog posts ✍️

***A Deep Dive into the Reformer***

\\
Madison May wrote a [new blog post](https://www.pragmatic.ml/reformer-deep-dive/) that provides a deep dive into [Reformer](https://ai.googleblog.com/2020/01/reformer-efficient-transformer.html), which is a new and improved Transformer-based model recently proposed by Google AI. We also featured Reformer in a [previous issue](https://medium.com/dair-ai/nlp-newsletter-reformer-deepmath-electra-tinybert-for-search-vizseq-open-sourcing-ml-68d5b6eed057) of the newsletter.

\\
***A free blogging platform***

\\
[fastpages](https://fastpages.fast.ai/fastpages/jupyter/2020/02/21/introducing-fastpages.html) allows you to automatically set up a blog using GitHub pages for free. This solution simplifies the process of publishing a blog and it also supports the use of exported word documents and Jupyter notebooks.

\\
***Tips for interviewing at Google***

\\
Pablo Castro, from the Google Brain team, published an [excellent blog post](https://psc-g.github.io/interviews/google/2020/02/25/interviewing-at-google.html) highlighting a list of tips for those interested in interviewing for a job at Google. Topics include advice on how to prepare for the interview, what to expect during the interview, and what happens after the interview.

\\
***Transformers are Graph Neural Networks***

\\
Both graph neural networks (GNNs) and Transformers have shown to be effective at different NLP tasks. To better understand the inner workings behind these approaches and how they relate, Chaitanya Joshi wrote a great [article](https://graphdeeplearning.github.io/post/transformers-are-gnns/) explaining the connection between GNNs and Transformers and different ways these methods can be combined in a sort of hybrid model.

\\
![](https://cdn-images-1.medium.com/max/800/0*u-BkejfKSKcnWOBx.jpg)

*Representing a sentence as a fully-connected word graph —* [*source*](https://graphdeeplearning.github.io/post/transformers-are-gnns/)

\\
***CNNs and Equivariance***

\\
Fabian Fuchs and Ed Wagstaff [discuss](https://fabianfuchsml.github.io/equivariance1of2/) the importance of equivariance and how CNNs enforce it. The concept of equivariance is first defined and then discussed in the context of CNNs with respect to translation.

\\
***Self-supervised learning with images***

\\
Self-supervised has been discussed a lot in previous issues of the NLP Newsletter due to the role it has played in modern techniques for language modeling. This [blog post](https://datasciencecastnet.home.blog/2020/02/22/self-supervised-learning-with-image%e7%bd%91/) by Jonathan Whitaker provides a nice and intuitive explanation of self-supervision in the context of images. If you are really interested in the topic, Amit Chaudhary also wrote an excellent [blog post](https://amitness.com/2020/02/illustrated-self-supervised-learning/) describing the concept in a visual way.


# Education 🎓

***Stanford CS330: Deep Multi-Task and Meta-Learning***

\\
Stanford recently released video recordings, in the form of a YouTube playlist, for their new [course on deep multi-task and meta-learning](https://www.youtube.com/playlist?list=PLoROMvodv4rMC6zfYmnD7UG3LVvwaITY5). Topics include bayesian meta-learning, lifelong learning, a reinforcement learning primer, model-based reinforcement learning, among others.

\\
***PyTorch Notebooks***

\\
dair.ai releases a [series of notebooks](https://github.com/dair-ai/pytorch_notebooks) that aim to get you started with deep neural networks using PyTorch. This is a work in progress and some current topics include how to implement a logistic regression model from scratch and how to program a neural network or recurrent neural network from scratch. Colab notebooks are also available in the GitHub repository.

\\
***The fastai book (draft)***

\\
Jeremy Howard and Sylvain Gugger release a [comprehensive list](https://github.com/fastai/fastbook) of draft notebooks for an upcoming course that introduces deep learning concepts and how to develop different methods using PyTorch and the fastai library.

\\
***Free Data Science courses***

\\
In case you missed it, Kaggle provides a series of [free micro-courses](https://www.kaggle.com/learn/overview) to get you started with your Data Science journey. Some of these courses include machine learning explainability, an intro to machine learning and Python, data visualization, feature engineering, and deep learning, among others.

\\
Here is another excellent [online data science course](https://lewtun.github.io/dslectures/) that provides a syllabus, slides, and notebooks on topics that range from exploratory data analysis to model interpretation to natural language processing.

\\
***8 Creators and Core Contributors Talk About Their Model Training Libraries From PyTorch Ecosystem***

\\
nepture.ai published an [extensive article](https://neptune.ai/blog/model-training-libraries-pytorch-ecosystem?utm_source=twitter&utm_medium=tweet&utm_campaign=blog-model-training-libraries-pytorch-ecosystem) that contains detailed discussions with core creators and contributors about their journey and philosophy of building PyTorch and tools around it.

\\
***Visualizing Adaptive Sparse Attention Models***

\\
Sasha Rush shares an impressive [Colab notebook](http://Visualizing%20Adaptive%20Sparse%20Attention%20Models) that explains and shows the technical details of how to produce sparse softmax outputs and induce sparsity into the attention component of a Transformer model which helps to produce zero probability for irrelevant words in a given context, improving performance and interpretability all at once.

\\
![](https://cdn-images-1.medium.com/max/800/1*7BB322LlVgt1zzk-cviSoA.png)


*Visualizing probability distribution of a softmax output*


# Noteworthy Mentions ⭐️

You can access the previous issue of the 🗞 NLP Newsletter [here](https://medium.com/dair-ai/nlp-newsletter-the-annotated-gpt-2-understanding-self-distillation-haiku-ganilla-sparkwiki-b0f47f595c82).

\\
Conor Bell wrote this nice [python script](https://gist.github.com/connorbell/9269401d127f1e507cc9aaf2803067c4) that allows you to view and prepare a dataset that can be used for a StyleGAN model.

\\
Manu Romero [contributes](https://github.com/huggingface/transformers/tree/master/model_cards/mrm8488/bert-spanish-cased-finetuned-pos) a fine-tuned POS model for Spanish. The model is available for use in the Hugging Face Transformer library. It will be interesting to see this effort in other languages.

\\
This [repo](https://github.com/tomohideshibata/BERT-related-papers) contains a long list of carefully curated BERT-related papers that approach different problems such as model compression, domain-specific, multi-model, generation, downstream tasks, etc.

\\
Connor Shorten published a short [15-minute video](https://www.youtube.com/watch?time_continue=79&v=-Bh_7tzyoR4&feature=emb_logo) explaining a new general framework that aims to reduce the effect of “shortcut” features in self-supervised representation learning. This is important because if not done right, the model can fail to learn useful semantic representations and potentially prove ineffective in a transfer learning setting.

\\
Sebastian Ruder published a new issue of the NLP News newsletter that highlights topics and resources that range from an analysis of NLP and ML papers in 2019 to slides for learning about transfer learning and deep learning essentials. Check it out [here](http://newsletter.ruder.io/issues/accelerating-science-memorizing-vs-learning-to-look-things-up-schmidhuber-s-2010s-greek-bert-arc-illustrated-reformer-annotated-gpt-2-olmpics-223195).


\\
[*Subscribe*](https://dair.ai/newsletter/) *🔖 to the NLP Newsletter to receive future issues in your inbox.*
