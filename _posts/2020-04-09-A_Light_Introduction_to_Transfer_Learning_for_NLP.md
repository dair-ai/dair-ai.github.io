---
layout: post
title: "A Light Introduction to Transfer Learning for NLP"
author: billy_rick
excerpt: "In this post, I will introduce transfer learning for natural language processing and key questions necessary to better understand this important area of study."
modified:
comments: true
tags: ""
image:
  thumb: transfer-learning.png
---

![](https://miro.medium.com/max/747/1*D-CoqzlBxj37_j-_vwMLxA.png)

\\
Picture this: a machine that can model and comprehend natural language and which is able to communicate in any language. Is this possible? Unfortunately, not yet. Because of the complexity of language, this only has credibility in the world of science fiction.

\\
But recent progress in machine learning (ML) and natural language processing (NLP) indicates that we are moving closer to teaching machines remarkable capabilities as it regards to natural language. I admit that the idea of a machine possessing human-level capabilities is pure hype given how complex language is to understand. Nevertheless, [recent progress](https://thegradient.pub/nlp-imagenet/) in NLP shows impressive results to be excited about.

\\
In this post, I will briefly introduce some of the recent ideas that could enable generalizable NLP systems, specifically those that employ transfer learning through pretrained language models. By generalizable, I mean NLP systems that are able to perform many tasks at once. For instance, just imagine a scenario where an ML algorithm is able to recognize both sentiment and sarcasm from textual information. Why not? What kind of machine learning technology is needed to achieve this? Enter the world of transfer learning.

### **Transfer learning**


In simple terms, transfer learning is the process of training a model on a large-scale dataset and then using that pretrained model to conduct learning for another downstream task (i.e., target task). Transfer learning was popularized in the field of computer vision thanks to the [ImageNet](https://en.wikipedia.org/wiki/ImageNet) dataset. Here I won’t discuss computer vision. Instead, I will focus on how these concepts are applied to the field of natural language processing.


### **Pretraining**

These are exciting times for NLP and ML researchers and enthusiasts. Very recently, pretrained language models were used to achieve state-of-the-art results on a wide range of NLP tasks (e.g., sequence labeling and sentence classification). Some of the recent works that employ pretrained language models include [ULMFit](https://arxiv.org/abs/1801.06146), [ELMo](https://allennlp.org/elmo), [GLoMo](https://arxiv.org/abs/1806.05662), and [OpenAI transformer](https://blog.openai.com/language-unsupervised/). These language modeling systems conduct deep pretraining of entire models with hierarchical representations or graph-based representations. This concept is a shift from the use of unary word embeddings, which have been effectively used to address many NLP tasks over the past few years, to the use of more sophisticated and abstract representations.

\\
You may be wondering, “How does pretraining work for NLP?” Why is pretraining useful? Simply put it, it just so happens that pretraining allows a model to capture and learn a varity of linguistic phenomena, such as long-term dependencies and negation, from a large-scale corpus. Then this knowledge is used (transferred) to initialize and then train another model to perform well on a specific NLP task, such as [sentiment classification](https://medium.com/dair-ai/state-of-the-art-multimodal-sentiment-classification-in-videos-1daa8a481c5a).

\\
This works in language because it happens, for example, that negation is an important attribute to detect sentiment polarity from textual information. In addition, negation could also be useful for, say, something like [sarcasm detection](https://medium.com/dair-ai/detecting-sarcasm-with-deep-convolutional-neural-networks-4a0657f79e80), which is one of the most complex, unsolved tasks in NLP. We can say that negation is useful for many NLP tasks and thus the pretrained model possesses some universal properties.

\\
A language model that possesses universal properties could be useful in cases where there is a lack of annotated datasets or language resources which is prevalent in NLP research. This idea is exciting because we are not only aiming to build a universal model, but also address some of the difficult challenges in ML research: *availability of data and language resources*.

### **The models**

So far we know that the knowledge obtained from pretrained language models, such as in the form of word embeddings, perform significantly well for many NLP tasks. The problem here is that this knowledge, in the form of latent features, is not broad or general enough to perform well on the target or downstream task/s at hand. There are many explanations for this — some of it we know and some we don’t — but for now, let us briefly look at one of the recent methods that aim to address these limitations.

\\
One recent, popular [method](https://arxiv.org/abs/1802.05365) coined as ELMo can be described as “pretraining the entire model with deep contextualized representations through stacked neural layers” as opposed to just employing the word embeddings (i.e., unary representations) as initialization. Don’t worry if it’s not clear what the above concept describes. My goal in this series is to clarify what these models are doing in a very intuitive manner, and answer several key questions that arise when considering them:

- What do we mean by modeling deep contextualized representations in the context of language? What is the model really learning?
- How to build and train these pretrained language models?
- What are the key components of the pretrained language models and how to improve them?
- How do we use or apply them to solve different language-based problems?
- What are the benefits of pretrained language models as compared to conventional transfer learning techniques for NLP?
- What are the drawbacks?
- What aspects of natural language do we need to keep in mind when pretraining language models?
- What kinds of pretraining tasks are we considering to build and test these so-called generalizable NLP systems?
- And more importantly, what kinds of datasets should we use that are representative enough to address the wide range of NLP tasks?

\\
I will stop with the questions here but you can already start to observe how complex this line of research is. It needs to be broken down into parts. All you need to understand for now is that in order to build a universal language model we need to consider many things, some of which are still not very clear today. In the next post of this series, I will begin to address each of these important questions while exploring the state-of-the-art research on transfer learning for NLP. *This post is part 1 of a series. There are a total of five parts to this series. Stay tuned for part 2. In the meantime, I encourage you to take a look at some of the links provided in this post.*
