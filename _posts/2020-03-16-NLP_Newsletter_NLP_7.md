---
layout: post
title: "NLP Newsletter #7 [EN]: NLP Paper Summaries, Learning to Simulate, Transformers Notebooks, Med7, Measuring Compositional Generalization, Neural Tangents,…"
author: billy_rick
excerpt: "In this issue, we cover topics that range from improving how to measure compositional generalization to a computer vision PyTorch library to a state-of-the-art physics simulator."
modified:
comments: true
tags: [nlp_newsletter]
image:
  thumb: nlp_newsletter_7.png
---

![](https://cdn-images-1.medium.com/max/1200/1*9gNslKwKiRaffDt2RSOgoQ.png)

\\
Welcome to the 7th issue of the NLP Newsletter. I hope you are having a wonderful day and that you and your loved ones are safe in these difficult times. We decided to publish this newsletter to bring some joy to our readers so please read when you have free time. For now, let’s keep focused on the things that are of top priority— our families and friends. ❤️ 💛 💚

\\
***A few updates about the NLP Newsletter and dair.ai***
All French and Chinese translations for the previous issues of the NLP Newsletter are now [available](https://github.com/dair-ai/nlp_newsletter). Find out how you can contribute to the translation of previous and upcoming issues of the NLP Newsletter at this [link](https://github.com/dair-ai/dair-ai.github.io/issues/11).

\\
We recently created two GitHub repositories that contain [NLP paper summaries](https://github.com/dair-ai/nlp_paper_summaries) and [PyTorch notebooks](https://github.com/dair-ai/pytorch_notebooks) to get you started with neural networks.


# Research and Publications 📙

***Measuring Compositional Generalization***

\\
In the context of machine learning, compositional generalization is the ability to learn to represent meaning and in turn sequences (novel combinations) from what’s learned in the training set. To this date, it is not clear how to properly measure compositionality in neural networks. A Google AI team [proposes](https://ai.googleblog.com/2020/03/measuring-compositional-generalization.html) one of the largest benchmarks for compositional generalization using tasks such as question answering and semantic parsing. The picture below shows an example of the proposed model using atoms (produce, direct, etc.) to produce novel compounds, i.e., combinations of atoms. The idea of this work is to produce a train-test split that contains examples that share similar atoms (building blocks to generate examples) distribution but different compound distribution (the composition of atoms). The authors claim that is a more reliable way to test for compositional generalization.

\\
![](https://cdn-images-1.medium.com/max/800/0*lXmUWOY8HJL7YVn1.gif)

*Credit: Google AI Blog*

\\
***Fine-Tuning Pretrained Language Models: Weight Initializations, Data Orders, and Early Stopping***

\\
Researchers ran a comprehensive [set of fine-tuning trials](https://arxiv.org/abs/2002.06305) to better understand the effect of weight initialization and early stopping in the performance of language models. Through various experiments that involved fine-tuning BERT hundreds of times, it was found that distinct random seeds produce very different results. In particular, the study reports that some weight initialization does perform well across a set of tasks. All the experimental data and trials were publicly released for other researchers that are interested in further understanding different dynamics during fine-tuning.

\\
***Zoom In: An Introduction to Circuits***

\\
OpenAI researchers published a [piece](https://distill.pub/2020/circuits/zoom-in/) discussing the state of interpretability of neural networks and the proposal of a new approach to interpreting them. Inspired by cellular biology, the authors delve deep into understanding vision models and what they learn by inspecting the weights of neural networks. Essentially, the study presented a few claims along with collected evidence that they believe could pave the way to better interpret neural networks.

\\
![](https://cdn-images-1.medium.com/max/800/1*i0c-qpiire6dD4IqJVKlYg.png)

\\
***NLP Research Highlights — Issue #1***

\\
In a new dair.ai series called [NLP Research Highlights](https://medium.com/dair-ai/nlp-newsletter-bertology-primer-fastpages-t5-data-science-education-pytorch-notebooks-slow-8ae5d499e040), we provide detailed descriptions of current interesting and important NLP research. This will serve as a way to keep track of NLP progress via approachable summaries of these works. In the first quarterly issue, topics range from improving language models to improving conversational agents to state-of-the-art speech recognition systems. These summaries will also be maintained [here](https://github.com/dair-ai/nlp_paper_summaries).

\\
***Learning to Simulate Complex Physics with Graph Networks***

\\
In the past few months, we have been featuring a lot about Graph Neural Networks (GNNs) due to their effectiveness not only in NLP but in other areas such as genomics and materials. In a recent [paper](https://arxiv.org/abs/2002.09405), researchers propose a general framework based on graph networks that is able to learn simulations in different domains such as fluids and deformable materials. The authors claim that they achieve state-of-the-art performance across different domains and that their general-purpose approach is potentially the best-learned physics simulator to date. Experiments include the simulation of materials such as goop over water and other interactions with rigid obstacles. They also tested a pre-trained model on out-of-distribution tasks and found promising results that show the generalization of the framework to larger domains.

\\
![](https://cdn-images-1.medium.com/max/800/1*48EolUDJoHpYRCTZxgn_qg.png)

[*(Sanchez-Gonzalez et al., 2020)*](https://arxiv.org/pdf/2002.09405.pdf)

\\
***Language-specific BERT models***

\\
Arabic BERT (AraBERT) is now available in the Hugging Face Transformer library. You can access the model [here](https://huggingface.co/aubmindlab/bert-base-arabert) and the paper [here](https://arxiv.org/abs/2003.00104). Recently, a Japanese version of BERT was also [released](https://github.com/akirakubo/bert-japanese-aozora). And there is also a Polish version of BERT called [Polbert](https://github.com/kldarek/polbert).


# Creativity, Ethics, and Society 🌎

***Computational predictions of protein structures associated with COVID-19***

\\
DeepMind releases [computationally-predicted structures](https://deepmind.com/research/open-source/computational-predictions-of-protein-structures-associated-with-COVID-19) for proteins linked with the virus related to COVID-19. The predictions are directly obtained from the AlphaFold systems but haven’t been experimentally verified. The idea with this release is to encourage contributions that aim to better understand the virus and how it functions.

\\
***Court cases that sound like the weirdest fights***

\\
Janelle Shane shares the [results](https://aiweirdness.com/post/612669075940900864/court-cases-that-sound-like-the-weirdest-fights) of a fun experiment where a GPT-2 model is fine-tuned to generate cases against inanimate objects. The model was fed a list of cases where the government was seizing contraband or dangerous goods and it generated cases like the ones shown in the picture below.

\\
![](https://cdn-images-1.medium.com/max/800/0*E5mHmkm1h4VQJ2Ni.png)

[*Source*](https://aiweirdness.com/post/612669075940900864/court-cases-that-sound-like-the-weirdest-fights)

\\
***Toward Human-Centered Design for ML Frameworks***

\\
Google AI [published](https://ai.googleblog.com/2020/03/toward-human-centered-design-for-ml.html) the results of a large-scale survey of 645 people who used TensorFlow.js. They aimed to find out from non-ML software developers what are the most important features and their overall experience with using current ML frameworks. Findings include that the “lack of conceptual understanding of ML” hinders the use of ML frameworks for this particular set of users. Participants in the study also reported the need for better instructions on how to apply the ML models to different problems and more explicit support for modification.

\\
***Face and hand tracking in the browser with MediaPipe and TensorFlow.js***

\\
This awesome [TensorFlow article](https://blog.tensorflow.org/2020/03/face-and-hand-tracking-in-browser-with-mediapipe-and-tensorflowjs.html?linkId=83996111) provides a walkthrough of how to enable real-time face and hand tracking on the browser using TensorFlow.js and MediaPipe.

\\
![](https://cdn-images-1.medium.com/max/800/0*XsRsB-tSOZo9yWOc.gif)

*Credit: TensorFlow Blog*


# Tools and Datasets ⚙️

***NLP Paper Summaries***

\\
We recently created a [repository](https://github.com/dair-ai/nlp_paper_summaries) containing a list of carefully curated NLP paper summaries for some of the most interesting and important NLP papers in the past few years. The focus is to feature paper summaries and blog posts of important papers to help improve the approachability and accessibility of NLP topics and research.

\\
***A differentiable computer vision library for PyTorch.***

\\
[Kornia](https://github.com/kornia/kornia) is an open-source library built on top of PyTorch that allows researchers to use a set of operators for performing differentiable computer vision using PyTorch. Some capabilities include image transformations, depth estimation, and low-level image processing, to name a few. It is heavily inspired by OpenCV but the difference is that it is meant to be used for research as opposed to building production-ready applications.

\\
![](https://cdn-images-1.medium.com/max/800/0*gN_-llcA4_3lIHYE.gif)

\\
***Introducing DIET: state-of-the-art architecture that outperforms fine-tuning BERT and is 6X faster to train***

\\
DIET (Dual Intent and Entity Transformer) is a natural language understanding (NLU) multitask architecture [proposed](https://blog.rasa.com/introducing-dual-intent-and-entity-transformer-diet-state-of-the-art-performance-on-a-lightweight-architecture/) by Rasa. The framework focuses on multitask training to improve results on both intent classification and entity recognition. Other benefits of DIET include the ability to use any of the current pre-trained embeddings such as BERT and GloVe. However, the focus was to provide a model that improves the current state-of-the-art performance on those tasks and is faster to train (6X speedup reported). The model is available in the [Rasa Open Source python library](https://rasa.com/docs/rasa/1.8.0/nlu/components/#dietclassifier).

\\
![](https://cdn-images-1.medium.com/max/800/0*R_8FOU-CVZabv7hJ.jpg)

[*DIET framework*](https://blog.rasa.com/introducing-dual-intent-and-entity-transformer-diet-state-of-the-art-performance-on-a-lightweight-architecture/?utm_source=twitter)

\\
***Lost in (language-specific) BERT models?***
[BERT Lang Street](https://bertlang.unibocconi.it/) is a neat website that provides the ability to search over 30 BERT-based models with 18 languages and 28 tasks with a total of 177 entries. For instance, if you wanted to find out the state-of-the-art results for sentiment classification using BERT models, you can just search for “sentiment” in the search bar (example shown in the screenshot below).

\\
![](https://cdn-images-1.medium.com/max/800/1*UuVno2eOAzYb_wlSSfukPA.png)

\\
***Med7***

\\
Andrey Kormilitzin releases [Med7](https://github.com/kormilitzin/med7) which is a model for performing clinical NLP (in particular named entity recognition (NER) tasks) on electronic health records. The model can identify up to seven categories and is available for use with the spaCy library.

\\
![](https://cdn-images-1.medium.com/max/800/1*yOMqhvTwYnxB4LYXv2Mgjg.png)

\\
***An Open Source Library for Quantum Machine Learning***

\\
[TensorFlow Quantum](https://ai.googleblog.com/2020/03/announcing-tensorflow-quantum-open.html) is an open-source library that provides a toolbox for rapid prototyping of quantum ML research that allows the application of ML models to approach problems ranging from medicine to materials.

\\
***Fast and Easy Infinitely Wide Networks with Neural Tangents***

\\
Neural Tangents is an open-source library that allows researchers to build and train infinite-width models and finite neural networks using JAX. Read the blog post of the release [here](https://ai.googleblog.com/2020/03/fast-and-easy-infinitely-wide-networks.html) and get access to the library [here](https://github.com/google/neural-tangents).

\\
![](https://cdn-images-1.medium.com/max/800/1*CojgKJwB_n_7-j0DJZ0y7g.png)

# Articles and Blog posts ✍️

***From PyTorch to JAX: towards neural net frameworks that purify stateful code***

\\
Sabrina J. Mielke published an [article](https://sjmielke.com/jax-purify.htm) that provides a walkthrough of how to build and train neural networks using JAX. The article focuses on comparing the inner workings of PyTorch and JAX when building neural networks, which helps to better understand some of the benefits and differences of JAX.

\\
![](https://cdn-images-1.medium.com/max/800/0*Nrw4UnmnIZ__elHu.png)

[*Source*](https://sjmielke.com/jax-purify.htm) **

\\
***Why do we still use 18-year old BLEU?***

\\
In this [blog post](https://ehudreiter.com/2020/03/02/why-use-18-year-old-bleu/), Ehud Reiter talks about why we still use old evaluation techniques like BLUE for evaluating NLP models for tasks like machine translation. As a researcher in the space, he also expresses the implications for techniques that perform the evaluation on more recent tasks.

\\
***Introducing BART***

\\
[BART](https://arxiv.org/abs/1910.13461) is a new model proposed by Facebook that involves a denoising autoencoder for pretraining seq2seq models that improve performance on downstream text generation tasks such as abstractive summarization. Sam Shleifer provides a [nice summary](https://sshleifer.github.io/blog_v2/jupyter/2020/03/12/bart.html) of BART and how he integrated it into the Hugging Face Transformers repo.

\\
***A Survey of Long-Term Context in Transformers***

\\
Madison May recently wrote an interesting [survey](https://www.pragmatic.ml/a-survey-of-methods-for-incorporating-long-term-context/) describing ways to improve Transformer based approaches, which include Sparse Transformers, Adaptive Span Transformers, Transformer-XL, compressive Transformers, Reformer, and routing transformer. We also touched on some of these topics in the dair.ai [publication](https://medium.com/dair-ai) and in this list of [paper summaries](https://medium.com/dair-ai/nlp-research-highlights-cd522b21b01a).

\\
***“Mind your language, GPT-2”: how to control style and content in automatic text writing***

\\
Despite the impressive fluency automatic text writing has exhibited in the past year, it is still challenging to control attributes like structure or content of the machine-written text. In a [recent blog post](https://creatext.ai/blog-posts/controllable-text-generation), Manuel Tonneau discusses the recent progress and the perspectives in the field of controllable text generation, from Hugging Face’s GPT-2 model fine-tuned on arXiv to Google’s T5, with mentions of Salesforce’s CTRL and Uber AI’s PPLM.

# Education 🎓

***Talk: The Future of NLP in Python***

\\
In one of our previous newsletters, we featured [THiNC](https://thinc.ai/) which is a functional deep learning library focused on compatibility with other existing libraries. This [set of slides](https://speakerdeck.com/inesmontani/the-future-of-nlp-in-python-keynote-pycon-colombia-2020?slide=9) introduces a bit more of the library which was used in the talk by Ines Montani for PyCon Colombia.

\\
***Transformers Notebooks***

\\
HuggingFace published a set of [Colab notebooks](https://github.com/huggingface/transformers/tree/master/notebooks) that help to get started with their popular Transformers library. Some notebooks include using tokenization, setting up NLP pipelines, and training a language model on custom data.

\\
![](https://cdn-images-1.medium.com/max/800/1*0AYHYUsHbaqV2vqN2zCzLQ.png)

\\
***TensorFlow 2.0 in 7 hours***

\\
Check out this [~7-hour free course](https://www.freecodecamp.org/news/massive-tensorflow-2-0-free-course/) on TensorFlow 2.0 containing topics that range from basic neural networks to NLP with RNNs to an introduction to reinforcement learning.

\\
***DeepMind: The Podcast***

\\
DeepMind has released all episodes (in the form of a [YouTube playlist](https://www.youtube.com/playlist?list=PLqYmG7hTraZBiUr6_Qf8YTS2Oqy3OGZEj)) for their podcast which features scientists, researchers, and engineers discussing topics that range from AGI to neuroscience to robotics.

\\
***Machine Learning and Deep Learning Courses***

\\
Berkeley is publicly releasing the [entire syllabus](https://sites.google.com/view/berkeley-cs294-158-sp20/home) for its course on “Deep Unsupervised Learning” mainly focusing on the theoretical aspects of self-supervised learning and generative models. Some topics include latent variable models, autoregressive models, flow models, and self-supervised learning, to name a few. Youtube videos and slides are available.

\\
We also found this [impressive list](https://www.reddit.com/r/MachineLearning/comments/fdw0ax/d_advanced_courses_update/) of advanced online courses on machine learning, NLP and deep learning.

\\
And here is another course called [“Introduction to Machine Learning](https://compstat-lmu.github.io/lecture_i2ml/index.html)” which includes topics such as supervised regression, performance evaluation, random forests, parameter tuning, practical advice, and much more.


# Noteworthy Mentions ⭐️

The previous NLP Newsletter (Issue #6) is available [here](https://medium.com/dair-ai/nlp-newsletter-bertology-primer-fastpages-t5-data-science-education-pytorch-notebooks-slow-8ae5d499e040).

\\
Connon Shorten published a [video](https://www.youtube.com/watch?v=QWu7j1nb_jI&feature=emb_logo) explaining the ELECTRA model which proposes a technique called replaced token detection to pre-train Transformers more efficiently. If you are interested, we also wrote a short summary of the model [here](https://medium.com/dair-ai/nlp-research-highlights-cd522b21b01a).

\\
Rachael Tatman is working on a new series called [NLP for Developers](https://www.youtube.com/watch?v=-G36q8_cYsc&feature=emb_logo) where the idea is to talk more in-depth about different NLP methods, when to use them and explaining common issues that you may run into.

\\
DeepMind releases [AlphaGo — The Movie](https://youtu.be/WXuK6gekU1Y) on YouTube to celebrate the 4th anniversary of AlphaGo beating Lee Sedol at the game of Go.

\\
OpenMined has [open positions](https://blog.openmined.org/introducing-openmined-research/) for Research Engineer and Research Scientist roles which is a good opportunity to get involved with privacy-preserving AI.

----------

If you have any datasets, projects, blog posts, tutorials, or papers that you wish to share in the next iteration of the NLP Newsletter, please free to reach out to me at ellfae@gmail.com or ****[**DM on Twitter**](https://twitter.com/omarsar0).

\\
[*Subscribe*](https://dair.ai/newsletter/) *🔖 to the NLP Newsletter to receive future issues in your inbox.*
