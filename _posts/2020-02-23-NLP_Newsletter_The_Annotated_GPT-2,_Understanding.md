---
layout: post
title: "NLP Newsletter: The Annotated GPT-2, Understanding self-distillation, Haiku, GANILLA, Sparkwiki, Ethics in NLP, Torchmeta,…"
author: billy_rick
modified:
comments: true
excerpt: "This issue covers topics such as understanding self-distillation, image-to-illustration translation, ethical considerations for NLP models, etc."
tags: [nlp_newsletter]
image:
  thumb: nlp_newsletter_5.png
---


![](https://cdn-images-1.medium.com/max/1200/1*YIhZsPaiBFkRMMWo5FAhGw.png)

\\
First of all, I can’t thank ❤️ all of you enough for the incredible support and encouragement to continue with the NLP Newsletter. This effort requires tedious research and editing which I find to be both rewarding and also useful to provide you the best content. Hope you are enjoying them because I do. 😉

\\
[*Subscribe*](https://dair.ai/newsletter/) *🔖 to the NLP Newsletter to receive future issues in your inbox.*

# Publications 📙

***A theoretical understanding of self-distillation***

\\
In the context of deep learning, [*self-distillation*](https://arxiv.org/pdf/1503.02531.pdf) is the process of transferring knowledge from one architecture to another identical architecture. Predictions of the original model are fed as target values to the other model while training. Besides having desirable properties, such as reducing model size, empirical results demonstrate that this approach works well on held-out datasets. A group of researchers recently published a paper that provides a theoretical analysis with the focus to better understand what is happening in this knowledge distillation process and why it is effective. Results show that a few rounds of self-distillation amplify regularization (by [*progressively limiting the number of basis functions that represent the solution*](https://twitter.com/TheGradient/status/1228132843630387201?s=20)) which tends to reduce over-fitting. (Read the full paper [**here**](https://arxiv.org/abs/2002.05715))

\\
![](https://cdn-images-1.medium.com/max/800/1*nWYO71awfooL4MrGK-tFww.png)

[*source*](https://arxiv.org/abs/2002.05715)

\\
***The 2010s: Our Decade of Deep Learning / Outlook on the 2020s***

\\
[Jürgen Schmidhuber,](http://people.idsia.ch/~juergen/) a pioneer in Artificial Intelligence, recently posted a [**new blog post**](http://people.idsia.ch/~juergen/2010s-our-decade-of-deep-learning.html) ****focusing on providing a historical overview of deep learning since 2010. Some topics include LSTMs, feedforward neural networks, GANs, deep reinforcement learning, meta-learning, world models, distilling NNs, attention learning, etc. The article concludes with an outlook on the 2020s encouraging attention to pressing issues such as privacy and data markets.

\\
***Using neural networks to solve advanced mathematics equations***

\\
Facebook AI researchers published a [**paper**](https://arxiv.org/abs/1912.01412) that claims to propose a model trained on math problems and matching solutions to learn to predict possible solutions for tasks such as solving integration problems. The approach is based on a novel framework similar to what’s used in *neural machine translation* where mathematical expressions are represented as a kind of language and the solutions being treated as the translation problem. Thus, instead of the model outputting a translation, the output is the solution itself. With this, the researchers claim that deep neural networks are not only good at symbolic reasoning but also for more diverse tasks.

\\
![](https://cdn-images-1.medium.com/max/800/1*P_JtxoC8pYkXuXCp3e3QeQ.png)

*Equations fed as input together with the corresponding solution outputted by the model —* [*source*](https://ai.facebook.com/blog/using-neural-networks-to-solve-advanced-mathematics-equations/)


# Creativity and Society 🎨

***AI for scientific discovery***

\\
Mattew Hutson [**reports**](https://www.sciencemag.org/news/2020/02/models-galaxies-atoms-simple-ai-shortcuts-speed-simulations-billions-times) how artificial intelligence (AI) can be used to produce emulators that have an important use in modeling complex natural phenomena that could, in turn, lead to different types of *scientific discovery*. The change with building these emulators is that they often require large-scale data and extensive parameter exploration. A recent [**paper**](https://arxiv.org/abs/2001.08055) proposes DENSE an approach based on [*neural architecture search*](https://en.wikipedia.org/wiki/Neural_architecture_search) to build accurate emulators while only relying on a limited amount of training data. They tested it by running simulations for cases including astrophysics, climate science, and fusion energy, among others.

\\
***Improving image-to-illustration translation***

\\
GANILLA is an approach that proposes the use of GANs to improve the transfer of both style and content in the unpaired [*image-to-image translation*](https://paperswithcode.com/task/image-to-image-translation) task. In particular, a model for image-to-illustration is proposed (with an improved generator network) and evaluated based on a new framework for quantitative evaluation that considers both content and style. The novelty of the work is in the proposed generator network that considers a balance between style and content which previous models fail to achieve. Code and pretrained models are made [available](https://github.com/giddyyupp/ganilla). Read the full paper [**here**](https://arxiv.org/abs/2002.05638).

\\
![](https://cdn-images-1.medium.com/max/800/1*l_B4vfaHVkXDwzM7SldiqQ.png)

\\
***Andrew Ng talks about interest in self-supervised learning***

\\
Andrew Ng, the founder of deeplearning.ai, joins the Artificial Intelligence podcast to [**talk**](https://www.youtube.com/watch?v=0jspaMLxBig) about topics including his early days doing ML, the future of AI and AI education, recommendations for proper use of ML, his personal goals and what ML techniques to pay attention to in the 2020s.

\\
Andrew explained why he is very excited about *self-supervised representation learning.* [**Self-supervised learning**](https://lilianweng.github.io/lil-log/2019/11/10/self-supervised-learning.html) involves framing a learning problem that aims to obtain supervision from the data itself to make use of large amounts of unlabeled data which is more common than clean labeled data. The representations, as opposed to the performance of the task, are important and can be used to address downstream tasks similar to what’s being used in language models such as [BERT](https://lilianweng.github.io/lil-log/2019/01/31/generalized-language-models.html#bert).

\\
There is also a lot of interest to use self-supervised learning for learning generalized visual representations that make models more accurate in low-resource settings. For instance, a recent method called [**SimCLR**](https://arxiv.org/abs/2002.05709) (led by Geoffrey Hinton) proposes a framework for *contrastive self-supervised learning* of visual representations for improving image classification results in different settings such as transfer learning and semi-supervised learning.

\\
![](https://cdn-images-1.medium.com/max/800/1*8zLzHFCyM3goc9y7KApHfg.png)

[*source*](https://arxiv.org/abs/2002.05709)


# Tools and Datasets ⚙️

***JAX libraries***

\\
[JAX](https://github.com/google/jax) is a new library that combines NumPy and automatic differentiation for conducting high-performance ML research. To simplify pipelines for building neural networks using JAX, DeepMind released [**Haiku**](https://github.com/deepmind/dm-haiku) and [**RLax**](https://github.com/deepmind/rlax). RLax simplifies the implementation of reinforcement learning agents and Haiku simplifies the building of neural networks using *familiar object-oriented programming models.*

\\
***A tool for processing Wikipedia data***

\\
[**Sparkwiki**](https://github.com/epfl-lts2/sparkwiki) ****is a tool to process Wikipedia data. This release is part of many efforts to enable interesting behavioral analytics research such as [capturing trends and language biases across different language editions of Wikipedia](https://arxiv.org/abs/2002.06885). The authors discovered that independent of language, the browsing behavior of Wikipedia users shows that they tend to share common interests for categories such as movies, music, and sports but differences become more apparent with local events and cultural particularities.

\\
![](https://cdn-images-1.medium.com/max/800/1*K7N9KbQlbuqowUeePjLtdw.jpeg)

\\
***Rust Tokenizers, DistilBERT base cased, Model cards***

\\
A new [**Transformers release**](https://github.com/huggingface/transformers/releases/tag/v2.5.0) by Hugging Face includes the integration of their fast tokenizer library which aims to speed up models like BERT, RoBERTa, GPT2, and other community-built models.


# Ethics in AI 🚨

***Ethical considerations for NLP and ML models***

\\
In a new [**episode**](https://soundcloud.com/nlp-highlights/106-ethical-considerations-in-nlp-research-emily-bender) of the [NLP Highlights,](https://soundcloud.com/nlp-highlights) Emily Bender and hosts talk about some ethical considerations when developing NLP models and technologies in the context of both academia and real-world usage. Some of the topics in the discussion include ethical considerations when designing NLP tasks, data collection approaches, and eventually publishing results.


\\
In addition to all the considerations above, a concern that is always discussed in the AI community is focusing too much on optimizing a metric, which goes against the foundations of what AI aims to achieve. Rachel Thomas and David Uminsky discuss where this can go wrong through a [**thorough analysis**](https://arxiv.org/abs/2002.08512) of different use cases. They also propose a simple framework for mitigating the problem which involves the use and combination of multiple metrics, followed by the involvement of those affected directly by the technology.


# Articles and Blog posts ✍️

***The Annotated GPT-2***

\\
Aman Arora recently published an exceptional blog post appropriately titled “[**The Annotated GPT-2**](https://amaarora.github.io/2020/02/18/annotatedGPT2.html)” explaining the inner workings of the Transformer based model called GPT-2. His approach was inspired by [The Annotated Transformer](https://nlp.seas.harvard.edu/2018/04/03/attention.html) that took an annotation approach to explain the important parts of the model through code and easy-to-follow explanations. Aman went through a great effort to re-implement OpenAI’s GPT-2 using PyTorch and the Transformers library by Hugging Face. It’s brilliant work!

\\
![](https://cdn-images-1.medium.com/max/800/1*oRFMJTEojyQ-uocVES5GYA.png)

[*source*](https://amaarora.github.io/2020/02/18/annotatedGPT2.html)

\\
***Beyond BERT?***

\\
Interesting [**take**](https://towardsdatascience.com/beyond-bert-6f51a8bc5ce1) by Sergi Castella on what lies beyond BERT. The main topics include improving metrics, how Hugging Face’s Transformers library empowers research, interesting datasets to look at, unpacking models, etc.

\\
***Matrix Compression Operator***

\\
The TensorFlow Blog published a [**blog post**](https://blog.tensorflow.org/2020/02/matrix-compression-operator-tensorflow.html?linkId=82298016) explaining the techniques and importance behind compressing matrices in a deep neural network model. *Matrix compression* can help to build more efficient tiny models that can be incorporated into smaller devices such as phones and home assistants. Focusing on the compression of the models via methods like *low-rank-approximation* and *quantization* means that we don’t need to compromise the quality of the model.

\\
![](https://cdn-images-1.medium.com/max/800/1*fpAdJvBIf4SKxF3gTIpe_g.png)

[*source*](https://blog.tensorflow.org/2020/02/matrix-compression-operator-tensorflow.html?linkId=82298016)


# Education 🎓

***Fundamentals of NLP***

\\
I am excited to release a draft of Chapter 1 of my new series called [**Fundamentals of NLP**](https://medium.com/dair-ai/fundamentals-of-nlp-chapter-1-tokenization-lemmatization-stemming-and-sentence-segmentation-b362c5d07684). It teaches NLP concepts starting from the basics while sharing best practices, important references, common mistakes to avoid, and what lies ahead in NLP. A Colab [notebook](https://colab.research.google.com/drive/18ZnEnXKLQkkJoBXMZR2rspkWSm9EiDuZ) is included and the project will be maintained [here](https://github.com/dair-ai/nlp_fundamentals).

\\
![](https://cdn-images-1.medium.com/max/800/1*mS5NcoJ_c8hYTjiJsuu_8g.gif)

\\
***[Online] Review/Discussion: Part I Mathematical Foundations Reading Session***

\\
Machine Learning Tokyo is hosting a remote online discussion reviewing chapters that were covered in their recent online study sessions. The group had previously studied chapters based on the book called [Mathematics For Machine Learning](https://mml-book.github.io/) written by Marc Peter Deisenroth, A Aldo Faisal, and Cheng Soon Ong. The [**event**](https://www.meetup.com/Machine-Learning-Tokyo/events/268817313/) is scheduled for March 8, 2020.

\\
***Book recommendations***

\\
In a previous segment, we discussed the importance of matrix compression for building tiny ML models. If you are interested to learn more about how to build smaller deep neural networks for embedded systems check out this great book called [**TinyML**](https://tinymlbook.com/?linkId=82595412) by Pete Warden and Daniel Situnayake.

\\
![](https://cdn-images-1.medium.com/max/800/0*omOa3aw2bfMzX2Qm.jpg)

[*source*](https://www.amazon.com/TinyML-Learning-TensorFlow-Ultra-Low-Micro-Controllers/dp/1492052043)

\\
Another interesting book to keep an eye on is the upcoming title **“**[**Deep Learning for Coders with fastai and PyTorch: AI Applications Without a PhD**](https://www.amazon.com/Deep-Learning-Coders-fastai-PyTorch/dp/1492045527)**”** by Jeremy Howard and Sylvain Gugger. The book aims to provide the necessary mathematical foundation to build and train models to approach tasks in the areas of computer vision and NLP.

\\
![](https://cdn-images-1.medium.com/max/800/0*i2OmtWOncatOYsZv.jpg)


[*source*](https://www.amazon.com/Deep-Learning-Coders-fastai-PyTorch/dp/1492045527)


# Noteworthy Mentions ⭐️

You can access the previous issue of the NLP Newsletter [here](https://medium.com/dair-ai/nlp-newsletter-pytorch3d-deepspeed-turing-nlg-question-answering-benchmarks-hydra-sparse-322f018ee096).

\\
[**Torchmeta**](https://arxiv.org/abs/1909.06576) is a library that allows ease of use of related data loaders for meta-learning research. It was authored by Tristan Deleu.

\\
Manuel Tonneau wrote a [**piece**](https://creatext.ai/blog-posts/machine-text-writing-gpt2-beam-search?utm_medium=newsletter) offering a closer look at some of the machinery involved in language modeling. Some topics include *greedy* and *beam search* and *nucleus sampling*.

\\
MIT [**releases**](http://introtodeeplearning.com/) the full syllabus and course schedule for the course titled “Introduction to Deep Learning”, including videos for lectures already delivered. They aim to release video lectures and slides every week.

\\
Learn how to train a model for named entity recognition (NER) using a Transformer based approach in under [**300 lines of code**](https://github.com/huggingface/transformers/blob/master/examples/ner/run_pl_ner.py). You can find the accompanying Google Colab [here](https://colab.research.google.com/drive/184LPlygvdGGR64hgQl3ztqzZJu8MmITn).

----------

If you have any datasets, projects, blog posts, tutorials, or papers that you wish to share in the next iteration of the NLP Newsletter, please free to reach out to me at ellfae@gmail.com or ****[**DM on Twitter**](https://twitter.com/omarsar0).

\\
[*Subscribe*](https://dair.ai/newsletter/) *🔖 to the NLP Newsletter to receive future issues in your inbox.*
