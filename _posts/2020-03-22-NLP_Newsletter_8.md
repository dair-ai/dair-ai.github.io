---
layout: post
title: "NLP Newsletter #8 [EN]: NeRF, CORD-19, Stanza, Text Generation 101, Notebooks, SECNLP, Dreamer,…"
author: billy_rick
excerpt: "This issue covers topics that range from synthesizing novel views of complex scenes to tutorials for text generation and transfer learning to survey papers on contextual embeddings and pretrained language models."
modified:
comments: true
tags: [nlp_newsletter]
image:
  thumb: nlp_newsletter_8.png
---


![](https://cdn-images-1.medium.com/max/1200/1*SptuncVzQw49OZFlDVaQdw.png)

# dair.ai updates
- We have added better categorization for all TL;DR and summaries included in the NLP paper summaries [repo](https://github.com/dair-ai/nlp_paper_summaries).
- All issues and translations of the NLP Newsletter are being maintained [here](https://github.com/dair-ai/nlp_newsletter).
- This week we also introduced [Notebooks,](https://github.com/dair-ai/notebooks) a hub for easily sharing data science notebooks with the community at large. If you have any notebooks that you would love to share with the community get in touch.
- We shared a [tutorial](https://colab.research.google.com/drive/1YuL0iqxaz09qR0_2Fgyi2wQHgil_Seqg) that provides steps on how to perform multiclass emotion classification using TextVectorization — an experimental feature in TensorFlow 2.1.0 that helps to manage text in a neural network.

# Research and Publications 📙

***Surveys on Contextual Embeddings and Language Models***

\\
This [paper](https://arxiv.org/abs/2003.07278v1) provides a light survey of approaches for learning contextual embeddings. It also includes a review of its applications for transfer learning, model compression methods, and model analyses. Another report involves a [summary](https://arankomatsuzaki.files.wordpress.com/2020/03/written_report.pdf) of methods used to improve Transformer based language models. Here is also another [comprehensive survey](https://arxiv.org/pdf/2003.08271.pdf) on pretrained language models which provides a taxonomy of NLP pretrained models.

\\
![](https://cdn-images-1.medium.com/max/800/1*1jLfdem3xZ0I3EVSyOy48g.png)

[*Qiu et al., 2020*](https://arxiv.org/pdf/2003.08271.pdf)

\\
***Visualizing Neural Networks with the Grand Tour***

\\
The Grand Tour is a linear approach (differs from the non-linear methods such as t-SNE) that projects a high-dimensional dataset to two dimensions. In a new Distill [article](https://distill.pub/2020/grand-tour/), Li et al. (2020) propose to use the Grand Tour capabilities to visualize the behavior of a neural network as it trains. Behaviors of interest in the analysis include weight changes and how it affects the training process, layer-to-layer communication in the neural network, the effect of adversarial examples when they are presented to the neural network.

\\
![](https://cdn-images-1.medium.com/max/800/1*XYCRZOzslb-ZRYlmtHV0Ng.png)

*Source:* [*Distill*](https://distill.pub/2020/grand-tour/)

\\
***Meta-Learning Initializations for Low-Resource Drug Discovery***

\\
It has been widely reported that meta-learning can enable the application of deep learning to improve on few-shot learning benchmarks. This is particularly useful when you have situations where there is limited data as is typically the case in drug discovery. A recent [work](https://arxiv.org/abs/2003.05996) applied a meta-learning approach called Model-Agnostic-Meta-Learning (MAML) and other variants to predict chemical properties and activities in low-resource settings. Results show that the meta-learning approaches perform comparably to multi-task pre-training baselines.

\\
***NeRF: Representing Scenes as Neural Radiance Fields for View Synthesis***

\\
An exciting work involving researchers from UC Berkeley, Google Research, and UC San Diego present a method ([NeRF](http://www.matthewtancik.com/nerf)) for synthesizing novel views of complex scenes. Using a collection of RGB image inputs, the model takes 5D coordinates (spatial location and direction), train a fully-connected DNN to optimize *a continuous volumetric scene function*, and outputs the volume density and view-dependent emitted RGB radiance for that location. The output values are composed together along a camera ray and rendered as pixels. These rendered differentiable outputs are used to optimize the scene representations *by minimizing the error of renderings all camera rays* from RGB images. Compared to other top-performing approaches for view synthesis, NeRF is qualitatively and quantitatively better and addresses inconsistencies in rendering such as lack of fine details and unwanted flickering artifacts.

\\
![](https://cdn-images-1.medium.com/max/800/1*E6RQL5jdtHXR98BJJREDYg.png)

\\
***Introducing Dreamer: Scalable Reinforcement Learning Using World Models***

\\
[Dreamer](https://ai.googleblog.com/2020/03/introducing-dreamer-scalable.html) is a reinforcement learning (RL) agent proposed to address some limitations (e.g. shortsightedness and computational inefficiency) present in model-free and model-based agents for solving difficult tasks. This RL agent, proposed by DeepMind and Google AI researchers, is trained to model the world that also provides the ability to learn long-sighted behaviors via backpropagation using the model predictions. SoTA results are achieved on 20 continuous control tasks based on the provided image inputs. In addition, the model is data-efficient and makes predictions in parallel, making it more computationally efficient. The three tasks involved in training the agent that achieve the different goals are summarized in the figure below:

\\
![](https://cdn-images-1.medium.com/max/800/1*DOlPDgvNu1kpTeogcLve-A.png)

*Source:* [*Google AI Blog*](https://ai.googleblog.com/2020/03/introducing-dreamer-scalable.html)

# Creativity, Ethics, and Society 🌎

***COVID-19 Open Research Dataset (CORD-19)***

\\
In an effort to encourage the use of AI to fight COVID-19, the Allen Institute of AI published the [COVID-19 Open Research Dataset (CORD-19)](https://pages.semanticscholar.org/coronavirus-research), a free and open resource to promote global research collaboration. The dataset contains thousands of scholarly articles that can allow NLP inspired research to obtain insights that can help in the fight against [COVID-19](https://www.who.int/emergencies/diseases/novel-coronavirus-2019).

\\
***SECNLP: A survey of embeddings in clinical natural language processing***

\\
[SECNLP](https://www.sciencedirect.com/science/article/pii/S1532046419302436) is a survey paper that includes a detailed overview of a wide variety of NLP methods and techniques applied in the clinical domain. The overview emphasizes mostly on embedding methods, problems/challenges addressed with embeddings, and discussion of future research directions.

\\
***AI for 3D Generative Design***

\\
This [article](https://blog.insightdatascience.com/ai-for-3d-generative-design-17503d0b3943) covers an approach that was used to generate 3D objects from natural language descriptions. The idea is to create a solution that allows a designer to quickly reiterate in the design process and be able to explore more broadly the design space. After creating a knowledge base of the design space consisting of 3D models and text descriptions, two autoencoders (see figure below) were used to encode that knowledge in a way that can be interacted with intuitively. The model put together can then accept a text description and generate a 3D design, try it out in this [demo](https://insight2020a.streamlit.io/starstorms9/shape/).

\\
![](https://cdn-images-1.medium.com/max/800/0*pbBv2Wa5QX7lUufY.png)

[*Source*](https://blog.insightdatascience.com/ai-for-3d-generative-design-17503d0b3943)


# Tools and Datasets ⚙️

***Stanza — A Python NLP Library for Many Human Languages***

\\
The Stanford NLP Group releases [Stanza](https://stanfordnlp.github.io/stanza/) (formerly StanfordNLP), a Python NLP library that provides out-of-the-box text analytic tools for more than 70 languages. Capabilities include tokenization, multi-word token expansion, lemmatization, POS, NER, and much more. The tool is built on top of the PyTorch library with support for using GPU and pretrained neural models. [Explosion](https://github.com/explosion/spacy-stanza) has also built a wrapper around Stanza that allows you to interact with Stanza models as a spaCy pipeline.

\\
***GridWorld Playground***

\\
Pablo Castro created an interesting [website](https://gridworld-playground.glitch.me/) that provides a playground for creating a Grid World environment to observe and test how a reinforcement learning agent tries to solve the Grid World. Some features include the ability to change the learning/environment parameters in real-time, change the position of the agent, and transfer values between two agents.

\\
![](https://cdn-images-1.medium.com/max/800/1*D1e6ixTEONl21t0UNmcaog.png)

\\
***X-Stance: A Multilingual Multi-Target Dataset for Stance Detection***

\\
[*Stance detection*](http://nlpprogress.com/english/stance_detection.html) is the extraction of a subject's reaction made to an actor’s claim which can be used for fake news assessment. Jannis Vamvas and Rico Sennrich recently published a [large-scale stance detection dataset](https://arxiv.org/abs/2003.08385) consisting of written text by electoral candidates in Switzerland. Multiple languages are available in the texts which could potentially lead to cross-lingual evaluations on the task of stance detection. The authors also propose the use of a multilingual BERT that achieves satisfactory performance on zero-shot cross-lingual and cross-target transfer. Learning across targets, in particular, is a challenging task so the authors used a simple technique involving standardized targets to train a single model on all the issues at once.

\\
***Create interactive textual heatmaps for Jupyter notebooks***

\\
Andreas Madsen created a Python library called [TextualHeatMap](https://github.com/AndreasMadsen/python-textualheatmap) that can be used to render visualizations that help to understand what parts of a sentence the model is using to predict the next word such as in language models.

\\
![](https://cdn-images-1.medium.com/max/800/0*IY3tKkznwarnRxdo.gif)

*Source:* [*textualheatmap*](https://github.com/AndreasMadsen/python-textualheatmap)


# Articles and Blog posts ✍️

***How to generate text: using different decoding methods for language generation with Transformers***

\\
HuggingFace published an [article](https://huggingface.co/blog/how-to-generate) explaining the different methods used for language generation in particular for Transformer based approaches. Among those techniques discussed are greedy search, beam search, sampling, top-k sampling, and top-p (nucleus) sampling. There are many articles like this out there but the authors spent more time explaining the practical side of these methods and how they can be applied via code snippets.

\\
***Training RoBERTa from Scratch — The Missing Guide***

\\
Motivated by the lack of a comprehensive guide for training a BERT-like language model from scratch using the Transformer’s library, Marcin Zablocki shares this detailed [tutorial](https://zablo.net/blog/post/training-roberta-from-scratch-the-missing-guide-polish-language-model/). The guide shows how to train a transformer language model for the Polish language with tips on what common mistakes to avoid, data preparation, pretraining configuration, tokenization, training, monitoring training process, and sharing the model.

\\
![](https://cdn-images-1.medium.com/max/800/0*PFPgjeUmzvazglqg.png)

# Education 🎓

***Getting started with JAX (MLPs, CNNs & RNNs)***

\\
Robert Lange recently published a comprehensive [tutorial](https://roberttlange.github.io/posts/2020/03/blog-post-10/) on how to train a GRU-RNN with JAX. In our [previous newsletter](https://medium.com/dair-ai/nlp-newsletter-nlp-paper-summaries-learning-to-simulate-transformers-notebooks-med7-measuring-de61fadd9db0), we also shared a couple of resources related to JAX.

\\
***NLP for Developers: Word Embeddings***

\\
Rachael Tatman published the first episode of a new series called NLP for Developers that will cover best practices on how to apply a wide range of NLP methods. The [first episode](http://youtube.com/watch?v=oUpuABKoElw&feature=emb_logo) includes an introduction to word embedding and how they are used and other common issues to avoid when applying them.

\\
***Thomas Wolf: An Introduction to Transfer Learning and HuggingFace***

\\
Thomas Wolf presented his [talk](https://www.youtube.com/watch?v=rEGB7-FlPRs&feature=youtu.be) on Transfer Learning for the NLP Zurich meetup providing a great introduction to transfer learning in NLP. The talk includes an overview of recent NLP breakthroughs and an introduction to Transformers and Tokenizers, two of the most popular libraries released by the HuggingFace team and contributors.

\\
![](https://cdn-images-1.medium.com/max/800/1*PMZ8ptBWo4wZ432kr-FXqA.png)


# Noteworthy Mentions ⭐️

Did you know that Google Sheets provides a free translation feature? Amit Chaudhary shares an [article](https://amitness.com/2020/02/back-translation-in-google-sheets/) that shows how to leverage the feature for back translation which is useful for augmenting your limited text corpus for NLP.

\\
New York NLP will be hosting an [online meetup](https://www.meetup.com/NY-NLP/events/269502774/) for a talk titled “Using Wikipedia and Wikidata for NLP” where the presenter will talk about how to leverage Wikipedia for different NLP projects and use cases.

\\
Lavanya Shukla wrote this nice [tutorial](https://app.wandb.ai/cayush/pytorchlightning/reports/Use-Pytorch-Lightning-with-Weights-%26-Biases--Vmlldzo2NjQ1Mw) on how to use PyTorch Lightning to optimize hyperparameters of a neural network while at the same time taking advantage of the simple code structures/styles provided in PyTorch Lightning. The resulting model and its performance using different hyper-parameters are visualized using the results produced by the WandB logger which can be provided as a logger parameter to a trainer object.

\\
A group of researchers published a [study](https://arxiv.org/abs/2003.07845) investigating more in detail why batch normalization (BN) tends to degrade performance in Transformer based methods applied to different NLP tasks. Based on those findings, the authors propose a new approach called power normalization to deal with issues found in BN. The method outperforms both BN and layer normalization (commonly used these days) on a variety of NLP tasks.

\\
This [blog post](https://www.datasciencecentral.com/profiles/blogs/10-timeless-reference-books) contains a long list of books to get you started with ML.

----------

If you have any datasets, projects, blog posts, tutorials, or papers that you wish to share in the next iteration of the NLP Newsletter, please free to reach out to me at ellfae@gmail.com or [send me a message on Twitter](https://twitter.com/omarsar0).

\\
[*Subscribe*](https://dair.ai/newsletter/) *🔖 to the NLP Newsletter to receive future issues in your inbox.*
