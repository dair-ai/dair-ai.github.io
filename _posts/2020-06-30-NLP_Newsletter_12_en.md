---
layout: post
title: "NLP Newsletter #12 [EN]: Hateful Memes, TextAttack, DETR, BLEURT, GameGAN, Survey Papers,…"
author: elvis
excerpt: "In this issue, we cover topics that range from progress in language modeling to Transformer-based object detection to how to stay informed with ML."
modified:
comments: true
tags: [nlp_newsletter]
image:
  thumb: nlp_newsletter_12.png
---

![](https://cdn-images-1.medium.com/max/1200/1*g36Zf0zqinVfWEfocBa0gA.png)

\\
Hello everyone! Welcome to the 12th issue of the NLP Newsletter. In this issue, we cover topics that range from progress in language modeling to Transformer-based object detection to how to stay informed with ML.

\\
It has been a month or so since we last published an issue of the NLP Newsletter. The hiatus is over and we are happy to bring back more of the interesting and creative works that have been coming out of the machine learning and natural language processing communities in the past few weeks.

\\
We have taken the time to think about how to improve the newsletter. We have received excellent feedback and we thank you for all the support.

# dair.ai updates

The dair.ai community has been producing incredible work and helping towards improving the democratization of education, research, and technologies. Here is what we have been up to the last few weeks:

- [ML Visuals](https://github.com/dair-ai/ml-visuals) is a new collaborative effort to help the machine learning community in improving science communication by providing free professional and compelling ML-related visuals and figures. You are free to use the visuals in your presentations or blog posts.
- Our [weekly paper discussion](https://github.com/dair-ai/ml-nlp-paper-discussions) attempts to bring together experts and beginners to help educate each other about recent NLP and ML papers. There are no requirements to join, just bring your willingness to learn and we will be happy to help along the way by answering questions and engaging in deeper discussions about ML papers.
- At the beginning of August, we are launching our first study group. We will be covering the excellent book called [“Dive into Deep Learning”](https://d2l.ai/index.html) by Aston Zhang, Zack C. Lipton, Mu Li, and Alex J. Smola. Learn more about this program on our [Meetup page](https://www.meetup.com/dair-ai/events/271394829/). There are no prerequisites but we will provide plenty of reading material to be better prepared for the lessons.
- Take a look at our recent talks on this [YouTube channel](https://www.youtube.com/channel/UCyna_OxOWL7IEuOwb7WhmxQ?view_as=subscriber). This effort aims to increase more awareness of the work of emerging NLP engineers and researchers. If you would like to give a talk please take a look at this [Call for Talks](https://github.com/dair-ai/dair-ai.github.io/wiki/Call-for-Talks).


# Research and Publications 📙

***Language Models are Few-Shot Learners***

\\
So far we have witnessed the success of Transformers models for a range of NLP tasks. Recently, [Brown et al. (2020)](https://arxiv.org/abs/2005.14165) proposed GPT-3, an autoregressive language model that builds on GPT-2, with a size of 175 billion parameters. This is the biggest LM model ever trained and aims to answer the question of whether scaling up the LM (in terms of size) improves the performance on many NLP tasks. In addition, the bigger question is whether the scaled-up LM can perform *few-shot learning* on these tasks and how that compares with other learning paradigms like fine-tuning, one-shot learning, and zero-shot learning. Interestingly enough, the model does very well on a variety of tasks but underperforms when dealing with tasks requiring some level of common-sense reasoning. The benefit of the large LM model seems to be that it doesn’t require fine-tuning (in a variety of cases) which means that some point it could be possible to easily expand to even more complex and novel downstream tasks without the need to collect supervised datasets.

\\
![](https://cdn-images-1.medium.com/max/800/1*QuDYXo8McJoYwCdlosVhWw.png)

*Source:* [*Brown et al. (2020)*](https://arxiv.org/abs/2005.14165)

\\
***Generating SOAP Notes from Doctor-Patient Conversations***

\\
Electronic health record (EHR) documentation involves a rigorous and long process typically prepared manually by physicians. This could potentially lead to stress and burnout in physicians as they need to spend long hours on this task. Motivated by this, [Khrisna et al. (2020)](https://arxiv.org/abs/2005.01795) propose an approach to help automate the generation of documentation in the form of SOAP notes. The authors experiment with different ML approaches leveraging conversations that happen between physicians and patients during a visit. Their approach combines extractive and abstraction modules trained in clinical conversations and achieve high ROUGE scores on the task of drafting SOAP notes.

\\
***BLEURT: Learning Robust Metrics for Text Generation***

\\
It is well known in the field of NLP that certain evaluation metrics (e.g., BLEU and ROUGE) are not the most reliable due to the poor correlation with human-based judgments, thus there have been more efforts recently to improve these metrics. [Sellam et al. (2020)](https://arxiv.org/abs/2004.04696) propose a learned evaluation metric called BLEURT that can better model human judgments. The text generation metric is based on BERT and aims to satisfy expressivity and robustness through pretraining on large amounts of synthetic data. When compared to other metrics (e.g., Meteor and BLEU) using the vanilla BERT models, BLEURT tends to better model human assessment and thus perform better in terms of accuracy.

\\
If you want an update of the different evaluation metrics used in NLP, this [recent survey](https://arxiv.org/abs/2006.14799) provides an in-depth discussion of evaluation in NLP.

\\
***Differentiable Reasoning over Text***

\\
Current search engines typically allow the use of a query to obtain relevant pages or information. However, they don’t do so well when retrieving answers to queries that involve multiple documents to arrive at an answer as is the case with multi-hop question answering. Current methods use either a retrieve + read (supported by a DNN) or a knowledge-base to perform some form of extraction to help address that particular task and find reasonable answers to those questions. The latter works well until the information scales up and the traversal on the knowledge graph becomes infeasible. Traversing the graph efficiently is important to lead to an answer. Bhuwan Dhingra proposes an [end-to-end system](https://blog.ml.cmu.edu/2020/05/15/differentiable-reasoning-over-text/) where the traversal operation is made differentiable and can be trained efficiently and effectively even on large corpus such as the entire Wikipedia dump. Using this approach the method is able to reason about text and answer questions, even those that require multiple hops. The author also provides a demo that showcases the system being used for multi-hop question answering.

\\
![](https://cdn-images-1.medium.com/max/800/0*fxVzcy6AV8V8fVp2.png)

*Source:* [*CMU Blog*](https://blog.ml.cmu.edu/2020/05/15/differentiable-reasoning-over-text/)

\\
***DE⫶TR: End-to-End Object Detection with Transformers***

\\
[Carion et al. (2020)](https://ai.facebook.com/research/publications/end-to-end-object-detection-with-transformers) propose a novel object detection algorithm that leverages the Transformer encoder-decoder architecture for object detection. DETR, as the model is called, is a non-autoregressive end-to-end system that makes predictions in parallel which allows the model to be fast and efficient. The novelty is in the direct use of a Transformer block to perform the object detection task which is framed as an image-to-set problem. This is chained with a CNN component that extracts the local information from images. This means that the Transformer component is in charge of reasoning about the image as a whole and output the final set of predictions in parallel. Overall the idea is to allow the reasoning of the relations between objects and the global image context which is useful for the prediction of objects in an image.

\\
![](https://cdn-images-1.medium.com/max/800/1*QjhCl88V3GzuXZWl-SGHHg.png)

*DETR high-level architecture —* [*source*](https://ai.facebook.com/research/publications/end-to-end-object-detection-with-transformers)

\\
***Survey Papers***

\\
If you are getting started with deep learning-based NLP most people recommend you start by learning to write code for classification tasks or data collection pipelines. Those are great but you also need to build intuition on the tasks or processes you are writing code for. These survey papers may help build intuition on deep learning based NLP and data collection:

- [Deep Learning Based Text Classification: A Comprehensive Review](https://arxiv.org/abs/2004.03705)
- [Contextual Word Representations: Putting Words into Computers](https://dl.acm.org/doi/pdf/10.1145/3347145?download=true)
- [Natural Language Processing Advancements By Deep Learning: A Survey](https://arxiv.org/abs/2003.01200)
- [A Survey on Data Collection for Machine Learning: a Big Data — AI Integration Perspective](https://arxiv.org/abs/1811.03402)

\\
***Discovering Symbolic Models from Deep Learning with Inductive Biases***

\\
[Cranmer et al. (2020)](https://arxiv.org/abs/2006.11287) developed a Graph Neural Network (GNN) approach to learning low-dimensionality representations that are then operated on to discover and extract physical relations through symbolic regression. By leveraging the strong inductive biases of GNNs, the proposed framework can be applied on large-scale data and trained to fit symbolic expressions to the internal functions learned by the model. By using GNs, the authors were able to train the model to learn interpretable representations and improve the generalization of it. The use cases addressed with the methodology include rediscovering of force laws, rediscovering Hamiltonians, and the application to a real-world astrophysical challenge (*predicting the excess amount of matter for a dark matter halo.*).

\\
![](https://cdn-images-1.medium.com/max/800/1*gS5npj4Y1CjGp64VXSMy4A.png)

*Figure by* [*Cranmer et al. (2020)*](https://arxiv.org/abs/2006.11287)


# Tools and Datasets ⚙️

***NLP datasets by HuggingFace***

\\
HuggingFace releases a Python library called [nlp](https://github.com/huggingface/nlp) which allows you to easily share and load data/metrics with access to ~100 NLP datasets. Some benefits of the library include interoperability with other ML libraries, fast execution, efficient memory usage, smart caching, and much more. Accompanying the library, they also provide a [website](https://huggingface.co/nlp/viewer/?dataset=glue&config=cola) for exploring datasets.

\\
![](https://cdn-images-1.medium.com/max/800/1*jTnEcrpdG2h4Yjj7WZ9zwQ.png)

\\
***Hateful Memes Challenge***

\\
The Hateful Memes Challenge is a competition to help build more effective multimodal systems for hate speech. As part of the challenge, a large-scale dataset called [Hateful Memes](https://www.drivendata.org/competitions/64/hateful-memes/) is provided that combines text and images, making it a challenging task. The dataset was created by Facebook AI and hosted by DrivenData. There is a $100000 total prize pool not to mention that the competition if part of the NeurIPS competition track as well. You will also be able to find [starter code](https://github.com/facebookresearch/mmf/tree/master/projects/hateful_memes) to get familiar with the task.

\\
![](https://cdn-images-1.medium.com/max/800/1*Gww3vx0kiT33gCxjKyk43w.png)

\\
***TextAttack***

\\
[TextAttack](https://github.com/QData/TextAttack) is a new Python framework for developing different NLP adversarial attacks and examining model outputs, increasing model generalization via data augmentation, and easily training NLP models using basic commands.

\\
***GameGAN***

\\
NVIDIA trained a new AI model called [GameGAN](https://blogs.nvidia.com/blog/2020/05/22/gamegan-research-pacman-anniversary/) that takes as input 50000 episodes of the popular PAC-MAN and learns the rules of the environment by looking at the screenplay involving an agent moving through the game. NVIDIA claims that this is the first neural network model that has the ability to mimic a computer game engineer by using GANs. This capability can be used by game developers to automate the generation of layouts for different game levels or even build more sophisticated simulator systems.

\\
***Question Understanding: COVID-Q: 1,600+ Questions about COVID-19***

\\
We have recently seen an explosion of NLP applications being used to better understand COVID-19 related datasets. Recently, a team of researchers has created a dataset consisting of ~1,600 COVID related questions annotated by question-category and question-type. Here are some useful links if you would like to know more about the project: [dataset on GitHub](https://github.com/JerryWei03/COVID-Q), [paper](https://arxiv.org/abs/2005.12522), and [blog post](https://towardsdatascience.com/what-are-people-asking-about-covid-19-a-new-question-classification-dataset-adcaeaddcce4). If you are interested in how to create such a dataset, one of the authors will present their experience creating this dataset in one of our online [meetups](https://www.meetup.com/dair-ai/events/271420297/).


# Articles and Blog posts ✍️

***Recipes for building an open-domain chatbot***

\\
Constanza Fierro recently [published](https://medium.com/dair-ai/recipes-for-building-an-open-domain-chatbot-488e98f658a7) an article discussing recipes for building an open-domain chatbot. The article aims to summarize a conversational agent proposed by Facebook AI, BlenderBot, which improves conversation through fine-tuning on datasets that focus on personality, empathy, and knowledge. One of the novelties of this work is the ability to train the models to generate and have more human-like dialog even with smaller models.

\\
***Machine Learning on Graphs: A Model and Comprehensive Taxonomy***

\\
This survey [paper](https://arxiv.org/abs/2005.03675) provides a comprehensive taxonomy of approaches that aim to learn graph representations. The authors introduce a new framework for unifying the different paradigms that exist for graph representation learning methods. This unification is important for better understanding the intuition behind the methods and further help in progressing this area of research.

\\
![](https://cdn-images-1.medium.com/max/800/1*sh_MUYhT1P1t-Vo44rzjpw.png)

*Source:* [*https://arxiv.org/abs/2005.03675*](https://arxiv.org/abs/2005.03675)

\\
***Zero-Shot Learning in Modern NLP***

\\
One of the ambitious goals of ML researchers is to create AI systems that have the ability to perform *zero-shot learning*, which in the context of NLP means to simply design and train a model to perform a task it wasn't explicitly trained to do. In other words, you can perform novel NLP tasks without any fine-tuning similar to what GPT-2 achieved on machine translation. If you want to learn more about recent approaches used for zero-shot learning in NLP, Joe Davidson has written an [extensive blog post](https://joeddav.github.io/blog/2020/05/29/ZSL.html) about the topic which even includes a demo and a Colab notebook.
Here is another [illustrated guide](https://amitness.com/2020/05/zero-shot-text-classification/) by Amit Chaudhary explaining how zero-shot learning is used for text classification.

\\
![](https://cdn-images-1.medium.com/max/800/0*i0L_fbFMBBNF7QFU.png)

*Source:* [*Amit Chaudhary*](https://amitness.com/2020/05/zero-shot-text-classification/)

\\
***AI Research, Replicability and Incentives***

\\
In a recent [blog post](https://dennybritz.com/blog/ai-replication-incentives/), Denny Britz discusses the issues of deep learning replicability and academic incentive systems and how these are driving some research trends in the community. Some of the topics discussed are the differences between reproduction and replication, computational budget, evaluation protocols, misunderstanding of open source, and top-down and bottom incentives. It’s an interesting article because it touches on topics such as the computational budget and reproducibility which are typically lacking in scientific reports. Denny also discusses the idea of the winning lottery ticket which states that just because you found a variant of the model that works for your experiments it doesn’t imply that it will generalize to data on different data distribution. In fact, in the majority of cases, the losing tickets or the rest of failed variations are not reported and what you get is typically a polished paper. So how can we replicate the full path to the conclusion?


# Education 🎓

***Fun Python***

\\
Rada Mihalcea [releases](https://web.eecs.umich.edu/~mihalcea/urls/FunPython.pdf) a comprehensive series of Python notebooks for getting up to speed with Python. The material covers basic concepts in Python and it was designed for students age 10–12.

\\
![](https://cdn-images-1.medium.com/max/800/1*6RD-wwbui3D8ZQOUV6nr5g.jpeg)

\\
***Deep Mind x UCL Deep Learning Lecture Series***

\\
DeepMind released a series of [free video lectures](https://www.youtube.com/playlist?list=PLqYmG7hTraZCDxZ44o4p3N5Anz3lLRVZF) covering topics in machine learning that range from advanced models for computer vision to generative adversarial networks to unsupervised representation learning.

\\
***Keras Code Examples***

\\
Over the past months, the community has been adding several recipes and [examples of code](https://keras.io/examples/) on the Keras website. The examples range from NLP models to computer vision algorithms to generative deep learning architectures. These types of resources that are community-driven help out the community to better understand how to train ML models for their own tasks and projects. If you can contribute, please do so, it helps people who are getting started.

\\
***Applied Machine Learning 2020***

\\
Andreas Muller releases [video recordings](https://www.youtube.com/watch?v=d79mzijMAw0&list=PL_pVmAaAnxIRnSw6wiCpSvshFyCREZmlM) for his course, Applied Machine Learning 2020. It includes topics like introduction to neural networks, time series and forecasting, topic modeling, clustering, etc.

\\
***Deep Learning Drizzle***

\\
Just in case you have a hard time finding NLP or ML courses, this [neat website](https://deep-learning-drizzle.github.io/) has one of the most comprehensive databases of online courses. Most of them are available as video lectures!

\\
![](https://cdn-images-1.medium.com/max/800/1*yV716lh60cVP0oHzKbPMXA.png)

*Source: Deep Learning Drizzle*

\\
***CMU Neural Nets for NLP 2020***

\\
Graham Neubig releases all [video lectures](https://www.youtube.com/playlist?list=PL8PYTP1V4I8CJ7nMxMC8aXv8WqKYwj-aJ) for the course called Neural Networks for NLP (2020 edition). The course covers topics like CNNs for text, efficiency tricks for NLP, attention, multitask and multilingual learning. It also contains accompanying notebooks with implementations of certain concepts covered in the course.

\\
***PyTorch Recipes***

\\
[PyTorch Recipes](https://pytorch.org/tutorials/recipes/recipes_index.html) are a collection of bite-sized PyTorch tutorials that aim to teach users about specific PyTorch features. They are meant to be easily consumed and are different from the lengthy tutorials that are also available on the website.

\\
![](https://cdn-images-1.medium.com/max/800/1*jcDapaNSSNuNx8f314WJKg.png)

# Stay Informed 🎯

In the last few years, we have witnessed an explosion of ML projects and papers. It has made it difficult to keep track of what’s happening and trending in ML. We have also seen incredible efforts from the community to help distill this fast-paced information. Starting today, we will include a special section in this newsletter showcasing some of the great resources that should help readers to keep track and stay educated on interesting and pressing issues in ML. Here is this week’s list:

- [**Underrated ML Podcast**](https://www.underratedml.com/) [](https://www.underratedml.com/)— a podcast that pitches underrated ML ideas
- [**Papers with Code**](https://paperswithcode.com/) [](https://paperswithcode.com/)— is a website to keep track of ML results and leaderboards and surface the latest ML papers with code to improve accessibility and accelerating progress.
- [**Made with ML**](https://madewithml.com/) — is a community-driven platform to stay up to date with the latest ML projects.
- [**ML Paper Discussions**](https://github.com/dair-ai/ml-nlp-paper-discussions) — a weekly discussion on recent ML and NLP papers
- [**Yannic Kilcher**](https://www.youtube.com/c/yannickilcher) ****— a YouTube channel providing excellent paper explanations


# Noteworthy Mentions ⭐️
- Deeplearning.ai [releases](https://www.coursera.org/specializations/natural-language-processing) the first two courses for their new NLP Specialization. Course 3 and 4 will be released soon.
- This [article](https://www.dropbox.com/s/ec3y4khbk38e29i/NeuralNetworksEN.pdf?dl=0) presents a mathematical overview of discriminative neural networks and generative neural networks. It was written by Gabriel Peyré.
- [YOLOv4](https://arxiv.org/abs/2004.10934) is the latest update of the popular object detection algorithm which aims to provide a faster algorithm to locate and classify objects.
- T5 is one of the latest works in NLP that aims to incorporate the lessons and techniques from previous works and establish a unified framework for address text-based tasks. If you are unfamiliar with how to use T5, Suraj Patil provides this [tutorial](https://colab.research.google.com/drive/176NSaYjc2eeI-78oLH_F9-YV3po3qQQO?usp=sharing) on how to fine-tune T5 using Transformers.
- [VidPress](http://research.baidu.com/Blog/index-view?id=134) is one of the latest tools built by Baidu to create videos directly from text articles.
- Here are some excellent [paper implementations](https://github.com/kushalj001/pytorch-question-answering) on the task of question answering using PyTorch. It provides detailed descriptions and code walkthroughs. This is work done by [Kushal](https://twitter.com/kushalj001).

[*Subscribe*](https://dair.ai/newsletter/) *🔖 to the NLP Newsletter to receive future issues in your inbox.*
